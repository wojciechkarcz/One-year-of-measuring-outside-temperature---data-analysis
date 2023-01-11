# One year of measuring outside temperature - exploratory data analysis

<img src="/img/comparision_mean_temp_to_30y_average.png" width="750" height="">

## OBJECTIVE

I built a [simple temperature sensor](https://github.com/wojciechkarcz/Simple-NodeMCU-temperature-sensor) based on NodeMCU board and DHT22. Throughout the year, I recorded air temperature and humidity measurements in front of my house. This is the exploratory data analysis of the data collected in 2021.

<br>  

## TOOLS

| Task      | Package / tools |
| --------- | ----------- |
| Data Collection | BeautifulSoup, requests, REST API|
| Data Cleaning   | pandas, json |
| Data Analysis   | pandas, numpy |
| Data Visualization   | matplotlib |
| Environment / Platforms   | python 3.8+, Jupyter Notebook|
<br>

## DATA COLLECTION

Temperature data was collected by the DHT22 sensor connected to the NodeMCU board. The data was saved every 10 minutes in a csv file on a home server.

For comparison purposes, data from official weather stations located nearby were also downloaded.

| Weather station | Distance from the DIY sensor | Data format | Technique |
| --------- | ----------- | ------------- | ------------- |
| Puławy | 22 km | zipped csv files | BeautifulSoup, requests, glob |
| Kozienice | 14 km | JSON | REST API, json |

<br>

## DATA PREPROCESSING

Data cleaning:

- parsing dates and handling time series data
- finding and replacing missing values
- merging data from multiple files into one dataframe
- multi-index handling

<br>

## DATA ANALYSIS

Questions that were sought for answers during the analysis:

- How the temperature was developing over the course of 2021?
- What was the average temperature in each month?
- How long did all the climatic seasons last? When did they start and when did they end?
- How does the temperature course in 2021 compare to the 30-year average for this region?
- How big were the temperature anomalies? Which month was clearly colder and which was warmer than the 30-year average ?
- What is the average temperature for each month over the last 15 years?
- How accurate is the DHT22 sensor compared to the nearest weather station?

<br>

## DATA VISUALIZATION

**Mean temperature by day in 2021**

<img src="/img/mean_temp_in_2021.png" width="450" height="">

---

**Mean temperature by month in 2021**

<img src="/img/mean_temp_by_month_in_2021.png" width="450" height="">

---

**Mean temperature distribution by month in 2021**

<img src="/img/mean_temp_distribution_by_month_in_2021.png" width="450" height="">

---

**Comparison of the temperature in 2021 to the 30-year average**

<img src="/img/comparision_mean_temp_to_30y_average.png" width="450" height="">

---

**Climatic seasons range in 2021**

<img src="/img/climatic_seasons_range_in_2021.png" width="450" height="">

---

**Mean temperature in April over last 30 years**

<img src="/img/mean_temp_in_April_over_30y.png" width="450" height="">

---

**Mean temperature by month heatmap**

<img src="/img/mean_temp_heatmap.png" width="450" height="">

---

**Temperature anomalies in 2021**

<img src="/img/temp_anomalies_in_2021.png" width="450" height="">

---

<br>

## RESULTS

- The mean temperature for each day is rarely close to the 30-year average. It usually oscillates between average maximum and minimum values.
- In 2021, there were no extreme temperature anomalies significantly exceeding the average maximum/minimum values (except for New Year's Eve and single days in November and August).
- This year June, July and November were significantly above the 30-year average. Generally it was very warm summer and warm autumn.
- On the other hand, in 2021 April was very cold (the coldest in 24 years). Also, the beginning of May and August were significantly cold compared to the 30-year average.
- It turned out that the DHT22 sensor overestimates the measurement especially around noon. However, the course of temperature changes is similar to the official measurements from the weather station.

<br>

## CONCLUSION

Even such a simple research project can provide interesting insights about weather changes in our area. Based on the data, it can be concluded that the weather in 2021 was mostly normal, matching the character of the temperate climate that dominates in Poland. From the distribution of average temperature anomalies in each month over the last 15 years, it can also be concluded that practically every year there are single significant anomalies (> +/- 3 degrees in relation to the 30-year average).

<br>

## FUTURE WORK

- Find a better place for the temperature sensor.
- Add new sensors to the weather station: atmospheric pressure sensor and ground temperature sensor.
- Change data storage to SQLite database instead of csv file.
- Create a simple online dashboard to monitor the weather in a more convenient way.
