# WEB REFERENCES:

## Datasets

- [Kaggle Dataset-US Funds dataset from Yahoo Finance](https://www.kaggle.com/datasets/stefanoleone992/mutual-funds-and-etfs)
- [Kaggle Dataset-Massive Yahoo Finance Dataset](https://www.kaggle.com/datasets/iveeaten3223times/massive-yahoo-finance-dataset)

## Python libraries to collect finantial data

### [yfinancy](https://github.com/ranaroussi/yfinance)
  - Descarga de precios históricos, dividendos, splits, y más.
  - Compatible con datos diarios, semanales, mensuales y otros intervalos.
  - Fácil de usar con pandas.
```python
import yfinance as yf
data = yf.download('AAPL', start='2020-01-01', end='2023-01-01')
print(data.head())
```

### [pandas-datareader](https://pandas-datareader.readthedocs.io/en/latest/)
- Compatible con Yahoo Finance, Google Finance (desactualizado), FRED, etc.
- Ideal para integrarse con pandas.
```python
import pandas_datareader as pdr
from datetime import datetime
start = datetime(2020, 1, 1)
end = datetime(2023, 1, 1)
data = pdr.get_data_yahoo('AAPL', start, end)
print(data.head())
```

### [investpy](https://github.com/alvarobartt/investpy)
- Amplia cobertura de mercados internacionales.
- Datos históricos y diarios de acciones, ETFs, bonos, criptomonedas, etc.
```python
import investpy
data = investpy.get_stock_historical_data(stock='AAPL',
                                          country='United States',
                                          from_date='01/01/2020',
                                          to_date='01/01/2023')
print(data.head())
```

### [Alpha Vantage](https://github.com/RomelTorres/alpha_vantage)
- Datos de acciones, divisas, criptomonedas y más.
- Requiere una clave de API gratuita (limitada en frecuencia de llamadas).
```python
from alpha_vantage.timeseries import TimeSeries
ts = TimeSeries(key='TU_API_KEY', output_format='pandas')
data, meta_data = ts.get_daily(symbol='AAPL', outputsize='full')
print(data.head())
```
 
### [Finnhub-Stock-API](https://github.com/finnhubio/Finnhub-API)
- Datos de acciones, criptomonedas, forex y noticias.
- Gratis con limitaciones.
```python
import finnhub
finnhub_client = finnhub.Client(api_key="TU_API_KEY")
data = finnhub_client.stock_candles('AAPL', 'D', 1577836800, 1609459200)
print(data)
```

### [yahooquery](https://github.com/dpguthrie/yahooquery)
- Descarga de datos fundamentales y financieros.
- Optimizada para consultas de múltiples activos.
```python
from yahooquery import Ticker
aapl = Ticker('AAPL')
data = aapl.history(period='5y')
print(data.head())
```

### [polygon.io](https://polygon.io)
- Datos en tiempo real y históricos.
- Orientada a traders y análisis de alta frecuencia.
- Requiere una clave de API (gratis y de pago).
```python
import requests
API_KEY = 'TU_API_KEY'
url = f'https://api.polygon.io/v2/aggs/ticker/AAPL/prev?apiKey={API_KEY}'
response = requests.get(url)
print(response.json())
```

### [IEX Cloud](https://publicapis.io/iex-cloud-api)
- Requiere suscripción (gratis con limitaciones).
- Amplia cobertura de activos financieros.
```python
import requests
API_KEY = 'TU_API_KEY'
url = f'https://cloud.iexapis.com/stable/stock/aapl/chart/1y?token={API_KEY}'
response = requests.get(url)
print(response.json())
```

