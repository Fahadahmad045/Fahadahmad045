
class BinanceAPIHelper:
    def __init__(self, api_key, api_secret):
        self.api_key = api_key
        self.api_secret = api_secret
        self.base_url = "https://api.binance.com/api/v3"

    def get_account_info(self):
        endpoint = "/account"
        params = {"timestamp": int(time.time()) * 1000}
        headers = {"X-MBX-APIKEY": self.api_key}
        response = requests.get(self.base_url + endpoint, params=params, headers=headers)
        return response.json()

    # Implement other functions similarly

# Example usage:
api_key = "your_api_key"
api_secret = "your_api_secret"
binance_helper = BinanceAPIHelper(api_key, api_secret)
account_info = binance_helper.get_account_info()
print(account_info) 
