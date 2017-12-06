# Crypto Signal Tracker

Track 250+ crypto currencies and their trading signals through Crypto Signal Tracker.

Technical Analysis Automated:
* Relative Strength Index (RSI)
* Ichimoku Cloud (Leading Span A, Leading Span B, Conversion Line, Base Line)
* Simple Moving Average
* Exponential Moving Average
* Breakouts

Features:
* Tracking for over 250 coins on Bittrex
* Email alerts for various signals
* Well documented script
* Automated Technical Analysis that's implemented from scratch for simplicity and ease of use
* Logging to track invalid/outdated coin pairs

You can build on top of this tool and implement algorithm trading and some machine learning models to experiment with predictive analysis.

Coming Soon:
* Bollinger Band
* Web Client


Shoutouts:
* Bittrex for an awesome API
* Eric Somdahl for writing the Python wrapper for the Bittrex API
* Abenezer Mamo for creating the [Crypto Signals](https://github.com/AbenezerMamo/crypto-signal) project which formed the foundation for this project
* Ryan Mullin for implementing the get_historical_data() method on v2 of the Bittrex API

# How to use
To install the dependencies for this project, run "pip install -r requirements.txt"  
Add a secrets.json file to the root directory of your project.
The contents of the file should mirror the following:

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

If you don't want to use the email notifications, you can remove the code

# How to run
Navigate to your file directory in terminal, run with "python app.py"

# Liability
I am not your financial adviser, nor is this tool. Use this program as an educational tool, and nothing more. None of the contributors to this project are liable for any loses you may incur. Be wise and always do your own research.