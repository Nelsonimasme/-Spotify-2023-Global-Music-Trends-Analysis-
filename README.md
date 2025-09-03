# -Spotify-2023-Global-Music-Trends-Analysis-
This project explores the **Spotify 2023 dataset**, which contains information about global music tracks, their performance across different streaming platforms, and their audio characteristics.




## **Project Overviews: Spotify 2023 Analysis**
---
This project explores the **Spotify 2023 dataset**, which contains information about global music tracks, their performance across different streaming platforms, and their audio characteristics. The main objective was to uncover insights into **streaming trends, artist performance, and track attributes** that can influence playlist curation and marketing strategies.




### **Problem Statements: Spotify 2023 Analysis**
---
With millions of tracks available across streaming platforms, it becomes challenging to:

* Identify which songs and artists drive the **highest engagement (streams, playlists, charts, etc.)**.
* Classify music by characteristics like **energy levels, BPM, and danceability** to better curate playlists.
* Compare performance across platforms (Spotify, Apple Music, Deezer, Shazam) to understand cross-platform popularity.
* Provide **data-driven recommendations** for future playlists and marketing strategies instead of relying on guesswork.
---
####  **Research Questions**

This project seeks to answer the following key questions:

1. **Top-Performing Tracks & Artists**

   * Which tracks have the highest number of streams in 2023?
   * Who are the top 3 artists dominating streaming platforms?

2. **Streaming Patterns**

   * What is the total number of streams for songs released in 2023?
   * How many tracks surpassed **100 million streams**?

3. **Musical Characteristics**

   * How are songs categorized by **energy levels** (High, Medium, Low)?
   * How many tracks fall within a **BPM range of 120–140**?
   * What is the average energy level of top artists’ songs?

4. **Cross-Platform Performance**

   * How do tracks perform across **Spotify playlists, Apple charts, Deezer, and Shazam**?

5. **Recommendations**

   * Which top 3 tracks should be prioritized for future playlists (based on streams + energy)?
   * Which artists should be given more spotlight in curated playlists?

---

This project aims to solve these challenges using the **Spotify 2023 dataset**, applying Python and data analysis techniques to uncover key insights.




### **Project Objectives: Spotify 2023 Analysis**
---

1. **Data Preparation & Cleaning**

   * Convert relevant columns (e.g., `streams`, `in_shazam_charts`, `in_deezer_playlists`) into numeric formats.
   * Handle missing or inconsistent values to ensure reliable analysis.

2. **Descriptive Analysis**

   * Calculate total and average streams across tracks.
   * Identify tracks with over **100M streams** and highlight top-performing songs.
   * Determine the most streamed track and the top-streamed artists.

3. **Categorization of Audio Features**

   * Classify songs into **High**, **Medium**, and **Low Energy** categories using nested IF logic.
   * Analyze BPM distributions, especially tracks within the **120–140 BPM** range.

4. **Visualization & Insights**

   * Generate bar charts to visualize **average energy by artist** (Top 10).
   * Annotate charts with exact values for clarity.
   * Highlight tracks with exceptionally high energy (>80%).

5. **Business-Oriented Insights**

   * Recommend top tracks for playlist inclusion based on **streams and energy levels**.
   * Identify top artists with the **highest overall streams**.
   * Provide actionable insights to optimize **playlist curation and marketing strategies**.
---



### **Data Collection: Spotify 2023 Analysis**
The dataset used for this project was obtained from **Spotify’s 2023 streaming data** (sourced through **Spotify API exports** )



### **Project Methodology: Spotify 2023 Analysis**

---

The methodology of this project is structured into six main stages to ensure a systematic and reliable analysis of the **Spotify 2023 dataset**.

#### **1. Data Collection**

* The dataset `spotify_2023.csv` was sourced, containing detailed information about:

  * Track names, artists, release years
  * Streaming statistics (Spotify, Apple, Deezer, Shazam)
  * Musical attributes such as BPM, Key, Mode, Energy, Danceability, Valence, etc.

#### **2. Data Cleaning & Preparation**

* Imported the dataset into **Pandas** for preprocessing.
* Resolved encoding issues (`encoding_errors=ignore`) to ensure all columns were properly read.
* Checked for missing values and inconsistencies.
* Converted relevant columns to the correct data types:

  * `streams` → **float**
  * `in_shazam_charts` → **integer**
  * `in_deezer_playlists` → **integer**
* Verified column integrity by inspecting headers and ensuring all expected fields were included.

#### **3. Data Transformation**

* Feature engineering was applied to enhance the dataset for analysis:

  * Created a new **energy category** column (High, Medium, Low) using nested IF logic.
  * Extracted **first 3 characters of track names** and **last 3 characters of artist names**.
  * Normalized numeric columns where necessary for better comparison.

#### **4. Exploratory Data Analysis**

Performed descriptive and comparative analysis to answer research questions:

* **Streams Analysis**

  * Total streams for tracks released in **2023**.
  * Total number of tracks with **100M+ streams**.
  * Identification of the **most streamed track**.

* **Tempo & Energy**
  * Count of tracks with **BPM between 120 and 140**.
  * Categorization of songs by **energy levels** (High, Medium, Low).

* **Artist Performance**
  * Top 3 most streamed artists.
  * Average energy level comparison across artists.

#### **5. Data Visualization**

* Used **Matplotlib** to generate insights visually:

  * **Bar charts** for top 10 artists by average energy.
  * Conditional formatting to highlight **top 5 streamed tracks** and tracks with **energy > 80%**.
  * Added **data labels** on visualizations for clarity (e.g., exact stream values above bars).

#### **6. Insights & Recommendations**

* Derived actionable insights from analysis:

  * Identified **top 3 tracks** to prioritize for playlists based on streams and energy.
  * Highlighted **top 3 artists** with the most streams as strong candidates for marketing focus.
  * Observed trends in BPM and energy for potential use in playlist curation strategies.
---



## **Data Collection: Spotify 2023 Analysis**

* The dataset was sourced from **Spotify 2023 track information** (via **Spotify API exports**).Each records is consist of :
* `track_name`
* `artist(s)_name`
* `artist_count`
* `released_year`
* `released_month`
* `released_day`
* `in_spotify_playlists`
* `in_spotify_charts`
* `streams`
* `in_apple_playlists`
* `in_apple_charts`
* `in_deezer_playlists`
* `in_deezer_charts`
* `in_shazam_charts`
* `bpm`
* `key`
* `Mode`
* `danceability_%`
* `valence_%`
* `energy_%`
* `acousticness_%`
* `instrumentalness_%`
* `liveness_%`
* `speechiness_%`



### **Data Pre-Proccessing: Spotify 2023 Analysis**
**Data Loading**: 
Reading the Raw Dataset which originally existed as a CSV file into a Pandas Dataframe
__Task:__ Follow the appropriate steps in reading a CSV file into a pandas Dataframe, 
and  Read the data stored  in the csv file named:  `spotify_2023` From your computer.
The resulting Dataframe should be named : `spotify_2023_df`




# Reading the CSV file into Pandas 

```python
#Solution
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
spotify_2023_df = pd.read_csv("C:/Users/HP/Downloads/spotify_2023.csv",  encoding_errors="ignore")

spotify_2023_df
```

<img width="829" height="340" alt="first" src="https://github.com/user-attachments/assets/9bfba6b4-cc7f-4858-bb66-80f3187bdb99" />




- **. Errors Encoding in the Data that got some columns header Missing**: 


```python
# Error Encoding 
# SOLUTION

spotify_2023_df = pd.read_csv(
    "C:/Users/HP/Downloads/spotify_2023.csv",
    sep=",",        # force comma, change to ";" if needed
    encoding="latin1",
    quotechar='"',  # handle text qualifiers
    engine="python" # better handling of messy CSVs
)

print(spotify_2023_df.columns)

```
<img width="508" height="99" alt="secon" src="https://github.com/user-attachments/assets/8e2818bb-1463-4c2c-a018-b2b0f70a6bbd" />



```python

# Checking if my CSV file is read correctly 
# SOLUTION
with open("C:/Users/HP/Downloads/spotify_2023.csv", "r", encoding="latin1") as f:
    for i in range(5):
        print(f.readline())

```
<img width="872" height="244" alt="Capture" src="https://github.com/user-attachments/assets/b33e7c58-fe38-4502-a3c9-186efc0b944a" />



```python

# Getting the complete dataset with the missing columns header

# SOLUTION

pd.set_option("display.max_columns", None)

spotify_2023_df

```

<img width="838" height="315" alt="Capture" src="https://github.com/user-attachments/assets/5cb99542-4ade-4b5b-9d2b-8b19c7cb6718" />




```python

# Counting the data

# SOLUTION

len(spotify_2023_df)

```
<img width="387" height="131" alt="Capture" src="https://github.com/user-attachments/assets/8a76befd-5e14-4e95-9e92-049cfa6fe3ca" />




### **Data Inspection and Cleaning**

- **1. inspecting the numerical columns**:

```python

  # SOLUTION

spotify_2023_df.describe()

```
<img width="824" height="224" alt="Capture" src="https://github.com/user-attachments/assets/f719c6fa-149f-4281-85a8-e308b56ea5ce" />



- **3. Check for Missing values**:

 
 ```python
# Checking is there are missing valus

# SOLUTION
print("Missing values per column:")

spotify_2023_df.isna().any()

```
<img width="251" height="344" alt="Capture" src="https://github.com/user-attachments/assets/44520917-5fe5-4aaf-a28a-2c4b26e48d31" />



```python
# Counting to total number of the data

# SOLUTION
len(spotify_2023_df)
```
<img width="328" height="87" alt="Capture" src="https://github.com/user-attachments/assets/84b72c19-5330-46d1-bf47-094d49419d1c" />




- **4. Counting the Missing values**:

 ```python

# counting the number of missing values 

# SOLUTION
total_no_of_missing_values = spotify_2023_df.isna().sum()
print("Below is The Total Number Of Missing Values")
print(total_no_of_missing_values)

```
<img width="264" height="335" alt="Capture" src="https://github.com/user-attachments/assets/67d48522-8150-47d2-9cff-6ef115d602c0" />




- **5. Visualizing the Missing values**:

```python

# SOLUTION

total_no_of_missing_values.plot(kind = "bar")

# show plot
plt.show()

```

<img width="372" height="307" alt="Capture" src="https://github.com/user-attachments/assets/d3df9308-0906-4f8a-af20-493f5a0b894a" />



- **. Checking  for the Data Type**:

```python

# Checking the data type

# SOLUTION
print(spotify_2023_df.dtypes) 

```
<img width="197" height="353" alt="Capture" src="https://github.com/user-attachments/assets/d63eb385-6636-454e-bb0b-f3f949bd6aa0" />




### **.Converting  Some Columns To thier Appropriate DataType**


```python

# Coverting , Streams, In_shazam_charts, and in_deezer_playlists to their appropriate datatype
# SOLUTION

# Condition 1
# Convert "streams" to float
spotify_2023_df["streams"] = pd.to_numeric(
    spotify_2023_df["streams"], errors="coerce"
).astype(float)


# Condition 2
# Convert "in_shazam_charts" to integer 
spotify_2023_df["in_shazam_charts"] = pd.to_numeric(
    spotify_2023_df["in_shazam_charts"], errors="coerce"
).astype("Int64")

# Condition 3
# Convert "in_deezer_playlists" to integer
spotify_2023_df["in_deezer_playlists"] = pd.to_numeric(
    spotify_2023_df["in_deezer_playlists"], errors="coerce"
).astype("Int64")

print(spotify_2023_df.dtypes)

```

<img width="228" height="354" alt="Capture" src="https://github.com/user-attachments/assets/d490ec9a-db55-44cf-8b74-f255e28e95df" />


```python
spotify_2023_df.isna().any()

```
<img width="235" height="347" alt="Capture" src="https://github.com/user-attachments/assets/1b443ff9-eb44-41f0-a485-bfc925a73143" />



### **Handling Missing Values** 

```python

# Replacing the mising values with 0

spotify_2023_df["in_shazam_charts"].mean()

spotify_2023_df["key"].mode()

# but we will be replacing it wit 0,

spotify_2023_df["in_deezer_playlists"].mean()

```
<img width="375" height="241" alt="Capture" src="https://github.com/user-attachments/assets/fb061bd3-b088-4327-bb67-6ee8bd963bab" />
































