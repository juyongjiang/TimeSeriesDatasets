# Datasets for Time Series Forecasting
> Time series are ubiquitous in today’s data-driven world. Given historical data, time series forecasting (TSF) as a long-standing task aims to predict future multi-step data. It has a wide range of applications, including but not limited to traffic flow estimation, energy management, economics investment, weather forecasting, and disease predictions. 

This repository collects public benchmark datasets for Time Series Forecasting (TSF), in which all the datasets are well pre-processed and can be used directly. According to whether to consider the correlations between sensors (nodes), we roughly divide them into two categories as follows: 

(1) Without Considering Correlation Between Sensors [[Google Drive](https://drive.google.com/drive/folders/16wqbX5UhlaIieLYdeN6h8kfHKx58bdtc?usp=sharing)] [[Baidu Wangpan]()(Password: )];

(2) Considering Correlation Between Sensors [[Google Drive](https://drive.google.com/drive/folders/1N-VnvZe6vYnvmWk-CZ1UC-BB9_f4jxw5?usp=sharing)] [[Baidu Wangpan]()(Password: )].

## Without Considering Correlation Between Sensors
### Brief Introduction of Datasets
- [ETT (Electricity Transformer Temperature)](https://github.com/zhouhaoyi/ETDataset):
This dataset consists of two `hourly-level` datasets (ETTh) and two `15-minute-level` datasets (ETTm). Each of them contains one oil and six load features of electricity transformers from July 2016 to July 2018.
- [Traffic](http://pems.dot.ca.gov):
This dataset from the California Department of Transportation describes the road occupancy rates between 0 and 1. It contains the `hourly` data recorded by the sensors of San Francisco Bay area freeways from 2015.01 to 2016.12. 
- [Electricity](https://archive.ics.uci.edu/ml/datasets/ElectricityLoadDiagrams20112014):
This dataset collects the `hourly` electricity consumption in KWh of 321 clients from 2012 to 2014. Note that, the raw dataset records every `15 minutes` from 2011 to 2014 while some dimensions of data are equal to 0. Thus, the records in 2011 are removed. 
- [Exchange-Rate](https://github.com/laiguokun/multivariate-time-series-data):
This dataset collects the `daily` exchange rates of 8 countries, including Australia, British, Canada, Switzerland, China, Japan, New Zealand and Singapore, from 1990.01 to 2016.12.
- [Weather](https://www.bgc-jena.mpg.de/wetter/):
This dataset includes 21 indicators of weather, such as air temperature, and humidity. Its data is recorded every `10 min` for 2020 in Germany.
- [ILI (Influenza-like Illness)](https://gis.cdc.gov/grasp/fluview/fluportaldashboard.html):
This dataset describes the ratio of <u>patients seen with influenza-like illness</u> and <u>the total number of the patients</u>. It includes the `weekly` data from the Centers for Disease Control and Prevention of the United States from 2002 to 2021.

### Statistics of Datasets 

## Considering Correlation Between Sensors
### Brief Introduction of Datasets

- PEMS

    PEMS03, PEMS04, PEMS07 and PEMS08 are collected by California Transportation Agencies (CalTrans) Performance Measurement System (PeMS) in real time every 30 seconds. The collected data is aggregated to 5 minutes, which means there are 12 points in the flow data for each hour. They can be downloaded from this [Repo](https://github.com/guoshnBJTU/ASTGNN/tree/main/data).

    - [PEMS03]():
    It contaions three months of statistics on traffic flow ranging from Sept. 1st 2018 to Nov. 30th 2018, including 358 sensors. The total number of observed traffic data points is 26,208.

    - [PEMS04]():
    It contaions two months of statistics on traffic flow, traffic speed and traffic occupancy rate ranging from Jan. 1st 2018 to Feb. 28th 2018, including 307 sensors. The total number of observed traffic data points is 16,992.

    - [PEMS07]():
    It contaions three months of statistics on traffic flow ranging from May 1st 2017 to Aug. 31st 2017, including 883 sensors. The total number of observed traffic data points is 28,224.

    - [PEMS08]():
    It contaions three months of statistics on traffic flow, traffic speed and traffic occupancy rate ranging from July 1st 2016 to Aug. 31st 2016, including 170 sensors. The total number of observed traffic data points is 17,856.

- [PEMS-BAY]():
This dataset is collected by California Transportation Agencies (CalTrans) Performance Measurement System (PeMS), and contains six months of statistics on traffic speed, ranging from Jan 1st 2017 to May 31th 2017, including 325 sensors in the Bay area. The total number of observed traffic data points is 16,937,179.
- [METR-LA]():
This dataset from loop detectors in the highway of Los Angeles County records four `months` of statistics on traffic speed, ranging from Mar 1st 2012 to Jan 30th 2012, including 207 sensors on the highways of Los Angeles County. The total number of observed traffic data points is 6,519,002.

### Statistics of Datasets 
- PEMS

    | Dataset | PEMS03    | PEMS04   | PEMS07 | PEMS08 |
    | ------- | --------- | -------- | ------ | ------ |
    | # of nodes |358|307|883|170|
    | # of timesteps |26,208|16,992|28,224|17,856|
    | # Granularity| 5 mins|5 mins|5 mins|5 mins|
    | # Start time|Sept. 1st 2018|Jan. 1st 2018|May 1st 2017|July 1st 2016|
    | # End time |Nov. 30th 2018|Feb. 28th 2018|Aug. 31st 2017|Aug. 31st 2016|
    | Signals|F|F,S,O|F|F,S,O|

    In column titled “Signals”, F represents traffic flow, S represents traffic speed, and O represents traffic occupancy rate.



## Evaluation Metrics
To evaluate the performance of models, there are three commonly used metrics, including **RMSE**, **MAE**, and **MAPE**.
Suppose $\textbf{X}=\{x_1, ..., x_n\}$ represents the ground truth, $\hat{\textbf{X}}=\{\hat{x}_1, ..., \hat{x}_n\}$ represents the predicted
values, and $\Omega$ denotes the indices of observed samples, the metrics are defined as follows.
* Mean Absolute Error (MAE):

$\text{MAE}(\textbf{X}, \hat{\textbf{X}})  = \frac{1}{| \Omega |}  \sum_{i \in \Omega} |x_i - \hat{x}_i|$
* Root Mean Square Error (RMSE):

$\text{RMSE}(\textbf{X}, \hat{\textbf{X}}) = \sqrt{\frac{1}{| \Omega |} \sum_{i \in \Omega} (x_i - \hat{x}_i)^2}$
* Mean Absolute Percentage Error (MAPE):

$\text{MAPE}(\textbf{X}, \hat{\textbf{X}})  = \frac{1}{| \Omega |}  \sum_{i \in \Omega} \left | \frac{x_i - \hat{x}_i}{x_i} \right|$

## Reference
- [1]. [https://github.com/laiguokun/multivariate-time-series-data](https://github.com/laiguokun/multivariate-time-series-data)
- [2]. [Modeling Long- and Short-Term Temporal Patterns with Deep Neural Networks](https://arxiv.org/abs/1703.07015)
- [3]. [Diffusion Convolutional Recurrent Neural Network: Data-Driven Traffic Forecasting](https://openreview.net/forum?id=SJiHXGWAZ)
- [4]. [Multi-Range Attentive Bicomponent Graph Convolutional Network for Traffic Forecasting](https://arxiv.org/abs/1911.12093)
- [5]. [Are Transformers Effective for Time Series Forecasting?](https://arxiv.org/abs/2205.13504)
- [6]. [Spatial-Temporal Synchronous Graph Convolutional Networks: A New Framework for Spatial-Temporal Network Data Forecasting](https://ojs.aaai.org/index.php/AAAI/article/view/5438)
- [7]. [Learning Dynamics and Heterogeneity of Spatial-Temporal Graph Data for Traffic Forecasting](https://ieeexplore.ieee.org/document/9346058)