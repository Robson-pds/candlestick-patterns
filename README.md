# candlestick-patterns
> Candlestick patterns detector

## Available patterns
* Inverted Hammer
* Hammer
* Hanging man
* Bearish/Bullish Harami
* Dark cloud cover
* Doji
* Doji Star
* Dragonfly doji
* Gravestone doji
* Bearish engulfing
* Bullish engulfing
* Morning star
* Morning star doji
* Piercing pattern
* Rain drop
* Rain drop doji
* Star
* Shooting star


## How to use
### Dataframe requirements

- Dataframe must contain open, high, low and close prices
- Open, high, low and close prices must be in numeric type.

#### Dataframe Example: 

|                time |     open |     high |      low |    close |
|--------------------:|---------:|---------:|---------:|---------:|
| 2019-12-21 00:00:00 |  7188.01 |  7190.58 |  7105    |  7132.75 |
| 2019-12-22 00:00:00 |  7131.59 |  7518.54 |  7122.47 |  7501.44 |
| 2019-12-23 00:00:00 |  7500.71 |  7695.38 |  7265.84 |  7317.09 |
| 2019-12-24 00:00:00 |  7317.3  |  7436.68 |  7157.04 |  7255.77 |
| 2019-12-25 00:00:00 |  7255.77 |  7271.77 |  7128.86 |  7204.63 |
| 2019-12-26 00:00:00 |  7205.01 |  7435    |  7157.12 |  7202    |
| 2019-12-27 00:00:00 |  7202    |  7275.86 |  7076.42 |  7254.74 |
| 2019-12-28 00:00:00 |  7254.77 |  7365.01 |  7238.67 |  7316.14 |
| 2019-12-29 00:00:00 |  7315.36 |  7528.45 |  7288    |  7388.24 |
| 2019-12-30 00:00:00 |  7388.43 |  7408.24 |  7220    |  7246    |
| 2019-12-31 00:00:00 |  7246    |  7320    |  7145.01 |  7195.23 |

### Code
```python
from candlestick import candlestick
df = candlestick.inverted_hammer(df, target='result')
```
### Result

| T                   | result            |     open |     high |      low |    close |
|:--------------------|:------------------|---------:|---------:|---------:|---------:|
| 2019-12-21 00:00:00 | False             |  7188.01 |  7190.58 |  7105    |  7132.75 |
| 2019-12-22 00:00:00 | False             |  7131.59 |  7518.54 |  7122.47 |  7501.44 |
| 2019-12-23 00:00:00 | False             |  7500.71 |  7695.38 |  7265.84 |  7317.09 |
| 2019-12-24 00:00:00 | False             |  7317.3  |  7436.68 |  7157.04 |  7255.77 |
| 2019-12-25 00:00:00 | False             |  7255.77 |  7271.77 |  7128.86 |  7204.63 |
| 2019-12-26 00:00:00 | True              |  7205.01 |  7435    |  7157.12 |  7202    |
| 2019-12-27 00:00:00 | False             |  7202    |  7275.86 |  7076.42 |  7254.74 |
| 2019-12-28 00:00:00 | False             |  7254.77 |  7365.01 |  7238.67 |  7316.14 |
| 2019-12-29 00:00:00 | False             |  7315.36 |  7528.45 |  7288    |  7388.24 |
| 2019-12-30 00:00:00 | False             |  7388.43 |  7408.24 |  7220    |  7246    |
| 2019-12-31 00:00:00 | False             |  7246    |  7320    |  7145.01 |  7195.23 |

"True" indicates that pattern is detected at that candle

## Parametrs
All pattern detection methods receive 3 parametrs:
* target (String) - Indicates the column to which the result of detection is saved as boolean. 
* is_reversed (Bool) - Pass True if rows in dataframe are in time descending order, otherwise false. Deafult is False.
* ohlc (List of String) - Pass list of strings which indicates the column names of open/high/low/close prices in dataframe. Default: ["open", "high", "low", "close"]. 
