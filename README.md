# Crypto Signal Tracker

## Introduction

Use Crypto Signal Tracker to track and simulate trades on 250+ crypto currencies by utilising their trading signals. This can be used to test the effectiveness of possible trading strategies.

#### Features:
* Tracking for over 250 coins on Bittrex
* Automated technical analysis (TA)
* Simulated trading analysis and tracking
* Email alerts for various signals
* Well documented script
* Automated Technical Analysis that's implemented from scratch for simplicity and ease of use
* Logging to track and document errors on the Bittrex API

You can build on top of this tool and implement algorithm trading and some machine learning models to experiment with predictive analysis.

#### Coming Soon:
* Bollinger Bands
* Web Client
* Back-Testing


#### Shoutouts:
* Bittrex for an awesome API
* Eric Somdahl for writing the Python wrapper for the Bittrex API
* Abenezer Mamo for creating the [Crypto Signals](https://github.com/AbenezerMamo/crypto-signal) project which formed the foundation for this project
* Ryan Mullin for implementing the get_historical_data() method on v2 of the Bittrex API

## How to setup
1) This project requires Python 3.X.X, which can be be found [here](https://www.python.org/ftp/python/3.6.3/python-3.6.3.exe)
2) To install the dependencies for this project, run `pip install -r requirements.txt`. If you receive a `'pip' is not recognized as an internal or external command` error, you need to add `pip` to your environmental `path` variable.
3) Add a directory named `database` the root directory of your project and add a `secrets.json` file to it. The contents of the file should mirror the following:

```json
{
    "bittrex": {
        "bittrex_key": "BITTREX_API_KEY",
        "bittrex_secret": "BITTREX_SECRET"
    },
    "gmail": {
        "address_list": [
            "EXAMPLE_RECIPIENT_1@GMAIL.COM",
            "EXAMPLE_RECIPIENT_2@GMAIL.COM",
            "ETC..."
        ],
        "username": "EXAMPLE_EMAIL@GMAIL.COM",
        "password": "GMAIL_PASSWORD"
    }
}
```

4) To use the Bittrex functionality, you need to setup the following:
     * `bittrex_key` is your Bittrex API key you can get from [here](https://bittrex.com/Manage#sectionApi)
     * `bittrex_secret` is your Bittrex API secret key

5) To use the Gmail functionality, you need to setup the following:
     * `username` is your gmail account's username (usually your account's email address)
     * `password` is your gmail account's password
     * `address_list` is the list of recipients you'd like to send emails to

If you don't want to use the email notifications, you can leave out the `gmail` code.

## How to run
Navigate to your file directory in terminal, and run with the command `python app.py`

## Simulated Trading
This system allows you to simulate and track crypto currency trades in order to test out different trading strategy. It uses a local database strategy to ensure data is not lost.

To use this functionality, first set the `number_of_strategies` variable, in the `app.py` file, to the number of strategies you wish to test.
You can then place your trading strategy code in the `buy_strategy` and `sell_strategy` functions also located in the `app.py` file.
Each of these functions have roughly the following structure:
```python
def x_strategy(coin_pair, strategy_index):
    # There's some setup and error check code here...
    if strategy_index == 0: # Execute code for strategy 0
        current_price = get_current_price(coin_pair)
        # TODO: Add you buy/sell strategy code here (ex: using the RSI and/or 24 hour trading volume)
        if your_buy_or_sell_condition: # If your indicators detect a buy/sell, add a simulated buy/sell to the database
            # There's some logging code here...
            
            # Add this buy/sale to the database
            Database_List[strategy_index].simulate_sell(coin_pair, current_price)
            
    if strategy_index == 1: # Execute code for strategy 1
        # TODO: Add strategy 1's code here
        
    if strategy_index == 2: # Execute code for strategy 2
        # TODO: Add strategy 2's code here
        
    # Etc...

```

See the source code for more examples.


## Liability
I am not your financial adviser, nor is this tool. Use this program as an educational tool, and nothing more. None of the contributors to this project are liable for any loses you may incur. Be wise and always do your own research.
