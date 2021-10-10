# Data source - Quick start

Dashboard widgets require a data source to display information about your devices. 
A data source allows you to target a specific telemetry item from your device, to visualize on your dashboard widgets.

Data sources can be one of two types, Raw or Statistical.

## Raw
A raw data source will return every telemetry entry logged by the device. Raw data sources are useful when you want to see absolutely every value your device has logged, 
but your dashboard performance will suffer if your device logs a large number of values.

Raw data sources allow the following statistical functions over the data:
- Average - average value
- Count - overall number of values
- Min - the lowest value
- Max - the highest value
- First - first value
- Last - last value

## Statistical
A statistical data source allows for telemetry entries to be aggregated over a given time unit. 
Statistical data sources are useful when your device logs a large number of values and you are more interested in seeing the trends in your data as opposed to the actual values.

Statistical data sources can be aggregated over the following time units:
- Seconds
- Minutes
- Hours
- Days
- Months
- Quarters
- Years

Statistical data sources allow the following statistical functions over the data:
- Average - average value
- Count - overall number of values
- Min - the lowest value
- Max - the highest value
- First - first value
- Last - last value
- Standard deviation - the standard deviation of all the values
- Slope - the difference in value divided by the difference in time between the first and last entries
