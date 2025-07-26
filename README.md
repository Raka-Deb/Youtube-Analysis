# YouTube Statistics Dataset - Exploratory Data Analysis (EDA) Report

## Introduction
This report presents the findings from an Exploratory Data Analysis (EDA) conducted on the "Global YouTube Statistics" dataset. The dataset contains information about YouTube channels, including their rank, subscriber count, video views, category, country, and various metrics related to earnings, engagement, and demographics. The goal of this analysis is to uncover key insights into the characteristics of top YouTube channels, their performance metrics, and relationships between variables.


![image alt](https://github.com/Raka-Deb/Youtube-Analysis/blob/ce7b1095cfeccd4decb8824a69b8b1721b829b1d/youtube-logo.png.webp)




The dataset was analyzed using Python with libraries such as `pandas`, `matplotlib`, and `seaborn`. The analysis includes data quality checks, descriptive statistics, and visualizations to explore trends and patterns.

---

## Dataset Overview
The dataset consists of **995 rows** and **28 columns**, each representing a YouTube channel and its associated attributes. Below is a summary of the columns:

- **rank**: Channel rank based on subscribers (1 to 995).
- **Youtuber**: Name of the YouTube channel.
- **subscribers**: Total number of subscribers.
- **video views**: Total video views for the channel.
- **category**: Category or genre of the channel (e.g., Music, Entertainment).
- **Title**: Channel title (may differ slightly from Youtuber name).
- **uploads**: Number of videos uploaded.
- **Country**: Country of origin of the channel.
- **Abbreviation**: Country code (e.g., IN for India).
- **channel_type**: Type of channel (e.g., Music, Games).
- **video_views_rank**: Rank based on video views.
- **country_rank**: Rank within the country.
- **channel_type_rank**: Rank within the channel type.
- **video_views_for_the_last_30_days**: Video views in the last 30 days.
- **lowest_monthly_earnings**: Estimated lowest monthly earnings.
- **highest_monthly_earnings**: Estimated highest monthly earnings.
- **lowest_yearly_earnings**: Estimated lowest yearly earnings.
- **highest_yearly_earnings**: Estimated highest yearly earnings.
- **subscribers_for_last_30_days**: New subscribers gained in the last 30 days.
- **created_year**: Year the channel was created.
- **created_month**: Month the channel was created.
- **created_date**: Day the channel was created.
- **Gross tertiary education enrollment (%)**: Education enrollment rate for the channel's country.
- **Population**: Population of the channel's country.
- **Unemployment rate**: Unemployment rate of the channel's country.
- **Urban_population**: Urban population of the channel's country.
- **Latitude**: Latitude of the channel's country.
- **Longitude**: Longitude of the channel's country.

---

## Data Quality Assessment

### Missing Values
The dataset contains missing values in several columns, which may impact analysis. The number of missing values per column is as follows:

- **category**: 46 missing values
- **Country**, **Abbreviation**, **Gross tertiary education enrollment (%)**, **Population**, **Unemployment rate**, **Urban_population**, **Latitude**, **Longitude**: 122-123 missing values each
- **channel_type**: 30 missing values
- **video_views_rank**: 1 missing value
- **country_rank**: 116 missing values
- **channel_type_rank**: 33 missing values
- **video_views_for_the_last_30_days**: 56 missing values
- **subscribers_for_last_30_days**: 337 missing values
- **created_year**, **created_month**, **created_date**: 5 missing values each

The high number of missing values in `subscribers_for_last_30_days` (337) suggests that recent subscriber growth data is incomplete for many channels. Similarly, country-related columns have significant missing data, possibly indicating channels without a specified geographic location.

### Duplicates
There are **no duplicate rows** in the dataset, ensuring that each channel is uniquely represented.

### Data Types
The dataset has a mix of data types:
- **Integer**: `rank`, `subscribers`, `uploads` (3 columns)
- **Float**: `video views`, `video_views_rank`, `country_rank`, `channel_type_rank`, `video_views_for_the_last_30_days`, `lowest_monthly_earnings`, `highest_monthly_earnings`, `lowest_yearly_earnings`, `highest_yearly_earnings`, `subscribers_for_last_30_days`, `created_year`, `created_date`, `Gross tertiary education enrollment (%)`, `Population`, `Unemployment rate`, `Urban_population`, `Latitude`, `Longitude` (18 columns)
- **Object**: `Youtuber`, `category`, `Title`, `Country`, `Abbreviation`, `channel_type`, `created_month` (7 columns)

The data types are appropriate for the respective columns, with numerical metrics (e.g., `subscribers`, `video views`) stored as integers or floats, and categorical variables (e.g., `category`, `Country`) stored as objects.

---

## Descriptive Statistics
The descriptive statistics provide an overview of the numerical columns in the dataset:

- **Subscribers**: 
  - Mean: ~22.98 million
  - Min: 12.3 million
  - Max: 245 million (T-Series)
  - The distribution is right-skewed, with a few channels having significantly higher subscriber counts.
- **Video Views**:
  - Mean: ~11.04 billion
  - Min: 0 (some channels, e.g., YouTube Movies, have no recorded views)
  - Max: 228 billion (T-Series)
  - The large standard deviation (14.11 billion) indicates high variability in video views.
- **Uploads**:
  - Mean: ~9,187 videos
  - Min: 0
  - Max: 301,308 (SET India)
  - The high maximum suggests some channels, particularly in the Shows category, upload a large number of videos.
- **Earnings**:
  - **Lowest Monthly Earnings**: Mean ~$36,886, Max $850,900
  - **Highest Monthly Earnings**: Mean ~$589,808, Max $13.6 million
  - **Lowest Yearly Earnings**: Mean ~$442,659, Max $10.2 million
  - **Highest Yearly Earnings**: Mean ~$7.08 million, Max $163.4 million
  - Earnings estimates show significant variability, reflecting differences in channel popularity and monetization potential.
- **Subscribers for Last 30 Days**:
  - Mean: ~349,079 new subscribers
  - Max: 8 million (MrBeast)
  - Only 658 channels have data for this metric, indicating incomplete coverage.
- **Created Year**:
  - Mean: 2012.63
  - Min: 1970
  - Max: 2022
  - Most channels were created between 2006 and 2016, with a few outliers from earlier years.

---

## Key Findings

### 1. Subscriber Distribution by Category
The average number of subscribers per category was analyzed to understand which types of content attract the most subscribers. The results, sorted in descending order, are as follows:

- **Shows**: 41.62 million (highest)
- **Trailers**: 39 million
- **Film & Animation**: 28.58 million
- **Nonprofits & Activism**: 27.75 million
- **Sports**: 27.11 million
- **Education**: 26.54 million
- **Music**: 25.72 million
- **Movies**: 25.65 million
- **Entertainment**: 21.40 million
- **People & Blogs**: 21.06 million
- **Gaming**: 20.85 million
- **News & Politics**: 20.63 million
- **Comedy**: 20.12 million
- **Howto & Style**: 19.39 million
- **Science & Technology**: 18.62 million
- **Pets & Animals**: 18.1 million
- **Autos & Vehicles**: 17.85 million
- **Travel & Events**: 12.5 million (lowest)

**Insights**:
- **Shows** and **Trailers** have the highest average subscriber counts, likely due to their broad appeal and association with established media brands (e.g., SET India).
- **Education** and **Music** categories also perform strongly, reflecting the popularity of educational content (e.g., Cocomelon) and music channels (e.g., T-Series).
- Niche categories like **Travel & Events** and **Autos & Vehicles** have lower subscriber counts, possibly due to their specialized audience.

### 2. Subscriber Growth by Creation Month
A line plot was created to visualize the average number of new subscribers gained in the last 30 days, grouped by the month the channel was created. Key observations:

- Channels created in **January** and **December** tend to have higher subscriber growth in the last 30 days, with averages peaking around 600,000–700,000 new subscribers.
- Channels created in **June** and **July** show lower subscriber growth, with averages around 200,000–300,000.
- The trend suggests that channels created at the start or end of the year may benefit from seasonal factors or strategic timing (e.g., aligning with New Year's resolutions or holiday content).

**Insights**:
- The variation in subscriber growth by creation month could be influenced by external factors like content seasonality or platform algorithm changes.
- Further analysis could explore whether specific categories (e.g., Music, Entertainment) drive these trends.

### 3. Top Channels
The top five channels by subscriber count are:
1. **T-Series**: 245 million subscribers, 228 billion views, Music category, India
2. **YouTube Movies**: 170 million subscribers, 0 views, Film & Animation category, United States
3. **MrBeast**: 166 million subscribers, 28.37 billion views, Entertainment category, United States
4. **Cocomelon - Nursery Rhymes**: 162 million subscribers, 164 billion views, Education category, United States
5. **SET India**: 159 million subscribers, 148 billion views, Shows category, India

**Insights**:
- **T-Series** dominates in both subscribers and views, reflecting the massive popularity of music content in India.
- **YouTube Movies** has an unusually high subscriber count but zero recorded views, which may indicate a data quality issue or a unique channel type (e.g., promotional or subscription-based).
- The top channels span diverse categories (Music, Entertainment, Education, Shows), highlighting the variety of successful content on YouTube.

### 4. Country Representation
The dataset includes channels from various countries, with the United States and India being prominently represented among the top channels. For example:
- **United States**: Home to MrBeast, Cocomelon, and YouTube Movies, with high tertiary education enrollment (88.2%) and a large urban population (~270 million).
- **India**: Home to T-Series and SET India, with a lower tertiary education enrollment rate (28.1%) but a massive population (~1.37 billion).

**Insights**:
- The dominance of U.S. and Indian channels may reflect large domestic audiences and strong digital infrastructure.
- Missing country data for 122 channels suggests that some channels may not be tied to a specific geographic location or that data collection was incomplete.

### 5. Earnings Insights
The estimated earnings (monthly and yearly) show significant variability:
- Channels like T-Series and SET India likely have high earnings due to their massive subscriber and view counts.
- The wide range between lowest and highest earnings (e.g., $0 to $13.6 million monthly) indicates that monetization potential depends heavily on factors like content type, audience engagement, and ad revenue models.

**Insights**:
- High-earning channels are likely in categories with broad appeal (e.g., Music, Shows) or those with consistent uploads (e.g., SET India with 116,536 uploads).
- The presence of zero earnings for some channels (e.g., YouTube Movies) may indicate non-monetized or promotional channels.

---

## Visualizations
The line plot for average subscribers gained in the last 30 days by creation month provided valuable insights:
- **Trend**: Peaks in January and December, with dips in June and July.
- **Implication**: Channels created during certain months may align with periods of high user engagement on YouTube.

Additional visualizations (not included in the provided code but recommended) could include:
- Bar plot of subscriber counts by category to highlight the dominance of Shows and Trailers.
- Scatter plot of subscribers vs. video views to explore the relationship between these metrics.
- Box plot of earnings by category to identify outliers and variability.

---

## Limitations
1. **Missing Data**: Significant missing values in `subscribers_for_last_30_days`, `Country`, and related columns limit the ability to draw conclusions for all channels.
2. **Data Quality Issues**: Anomalies like YouTube Movies having zero views despite high subscribers suggest potential errors or inconsistencies.
3. **Static Snapshot**: The dataset represents a single point in time, which may not capture seasonal trends or recent changes in channel performance.
4. **Earnings Estimates**: The earnings columns are estimates and may not reflect actual revenue due to variations in monetization strategies.

---

## Recommendations for Further Analysis
1. **Handle Missing Data**: Impute missing values (e.g., using median for numerical columns or mode for categorical columns) or exclude incomplete records for specific analyses.
2. **Correlation Analysis**: Explore correlations between subscribers, video views, uploads, and earnings to identify key drivers of channel success.
3. **Category Deep Dive**: Analyze specific categories (e.g., Music, Education) to understand content strategies that lead to high subscriber growth.
4. **Geographic Trends**: Investigate the impact of country-specific factors (e.g., population, internet penetration) on channel performance.
5. **Time Series Analysis**: If additional data is available, analyze subscriber and view growth over time to identify seasonal patterns.

---

## Conclusion
The EDA of the Global YouTube Statistics dataset reveals a diverse landscape of top YouTube channels, with significant variation in subscriber counts, video views, and earnings across categories and countries. Channels in the **Shows**, **Trailers**, and **Music** categories dominate in terms of subscribers, while channels created in January and December show higher recent subscriber growth. The dataset provides valuable insights into the factors driving YouTube channel success, but missing data and potential inconsistencies warrant careful consideration in future analyses.

This report serves as a foundation for deeper investigations into YouTube channel performance and can guide content creators, marketers, and researchers in understanding the dynamics of the platform.
