# Australian-Post-Pandemic-Labour-Market-Analysis-

##1. Background

Despite the unprecedent steps to contain the spread of the virus and government support packages to mitigate its impact on individuals, households, and businesses, we began to see huge impacts in the economy worldwide and unprecedent change in the labour market. As highlighted in the Australian Bureau of Statistics ’s figures, between March and April, the number of unemployed people increased by around 100, 000 and unemployment rate increased by 1.0 percent to 6.2 percent. This figure can only partially indicate the impact on labour market. More importantly there are many people who had their working hours reduced or were stood down. The unemployment rate only captures the population who were not employed and had been actively looking for work during the survey weeks. There are also many people who lost the job during March-April period who were either not looking for work or not available for work. These people were counted as not in the labour force, instead of being unemployed. Hence, this notebook will not only analyse the change in unemployment situation, it will also capture the change in participation rate, monthly hours worked and underemployment.

##2. Datasets

The datasets used for analysis in this notebook were obtained from Australian Bureau of Statistics website. The datasets are updated monthly by the ABS. The datasets used in this notebook were released on the 14th May 2020. They contain Labour Force data from Jan 1978 to April 2020. The data is normally collected through face-to-face, telephone and online interviews by the ABS with rotating groups. To mitigate the potential risks from COVID-19, the data collection for March and April were mainly carried out through telephone and online.  This resulted in a fall in the response rate for this rotation group. Consequently, the ABS decided to reduce the influence of that group. To avoid the seasonal impact in the employment, the datasets selected in this notebook are seasonally adjusted. 

##3. Data Analysis

###3.1 Data Selection

Based on the focus of the analysis, the following four datasets were selected:

1)	Australian Labour Market data: it contains the statistics for labour force status by gender from Jan 1978 to April 2020. It includes (un)employed total, employed full-time(part-time), unemployment rate, employment to population ratio etc. 

2)	Underutilized persons by Age and Gender: this dataset contains both underemployed figures caused by different reasons and ones categorized by age groups from 2014 to 2020. 

3)	Monthly hours worked by Employment Type by Sex and by State: this dataset is as the name stated, including the monthly hours worked by genders by employment type and state from July 1978 to April 2020. However, there is no data for territories (Northern Territory and Australian Capital Territory)

4)	Monthly hours worked in all jobs by employment type by Sex and Territory: This dataset contains the monthly hours worked data in Northern Territory and Australian Capital Territory, which complement with the last dataset


###3.2 Data Preparation

The four datasets selected have slightly different timeframes. Datasets were cleaned separately instead of being concatenated altogether. This approach is used to avoid data loss that is not covered by all the dataset’s timeframes. The data cleaning steps are as followings: 

1)	The two datasets regarding monthly hours worked complement one another.  These two data frames were concatenated based on datetime index. This resulted in four datasets becoming three. 

2)	The first step of data cleaning is to view the head of each dataset and explore the columns. Seasonally adjusted data means trends and original dates provided in the datasets need to be dropped. 

3)	Information such as ‘Unit’, ‘Series Type’ and ‘Series ID’ etc. which is embedded in the headings are used by ABS to record dataset details. This is not relevant for the data analysis and, subsequently, is dropped. 

4)	The next step of data preparation was to remove unwanted characters from column names. Symbols like ‘;’, ‘>>’ and extra spaces are contained in the column names. To organize the column format, those unwanted symbols and spaces were removed. Unnecessary words in column names were cut to shorten and make these more concise. The figure unit (000) or (%) were not reflected through the data, the units were added to column names for better understanding. 

5)	To effectively analyse the time series data, the index has been converted to Datetime Index and new columns for month and year have been generated for further use. 

6)	The date types found in the data were expressed as objects. Int or float are required for calculation, so these objects were converted to a manageable data type.

7)	To obtain more insight about the data, more calculations were done. In preparing the national labour market data, columns like ‘Not in the labour force (000)’, ‘Employed total growth (000)’ were generated. Similarly, underemployment rate for different genders and different age groups were calculated for underutilized data, monthly hours worked per thousand people were calculated for each state. 

8)	The cleaned data was saved in csv format ready for analysis. 

###3.3 Data Analysis

Data was analysed based on timeframe—Overall Change from 1978 to 2020, Change over last 5 years and Current situation based on data from April 2020. 

1)	Employment Change from 1978 to 2020—this section visualises the change in total employed population, unemployment rate, participation rate and monthly hours worked during this period. Additional graphs demonstrate the April worked hours change from 1978 to 2020 and the correlation between unemployment rate and employment to population ratio during this four decades. 

2)	Employment Change Over Last 5 Years – this section focuses on the labour market change since 2015, this relates to the employment change by employment status and how the underemployment changed in different employment types. 

3)	Current Employment Situation – the last analysis section emphasises the change in the labour market during April 2020. The pie charts visualise the components of employment and labour force participation. The three horizontal bar charts showcase that in April 2020 working hours per thousand people in each state worked, how the underemployment impacted different age groups and the reasons which made people underemployed. 

##4. Conclusion

The data analysis has found the current COVID-19 pandemic had a huge impact on the Australian Labour Market. Not only has the unemployment rate increased exponentially, the other employment indicators: participation rate, employment to population ratio and monthly hours worked all see a sharp drop during the April 2020 period. Due to the restriction to slow the virus spread and businesses shutting down, the Australian Labour Market saw a large amount of people either unemployed or not counted in the labour force. Even for people who still have full-time or part-time employment, the data analysis indicates that their monthly hours worked dropped tremendously, with many of them suffering from underemployment. 
