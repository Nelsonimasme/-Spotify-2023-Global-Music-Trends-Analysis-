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


- **. Reconfirming if there are still Missing values**: 

```python

spotify_2023_df.isna().any()

```
<img width="247" height="326" alt="Capture" src="https://github.com/user-attachments/assets/f4ce59d3-fe48-4fdc-9dbd-1aefecf059cc" />




- **. Check for  Duplicates**:

```python
# Recounting the data to confirm is there are still missing values

#Solution
len(spotify_2023_df)

```
<img width="471" height="85" alt="Capture" src="https://github.com/user-attachments/assets/ab22b3a1-297e-4ed2-b002-b58a49d74bf1" />



- **.Dropping of Duplicates**:

```python

# Droping any duplicates 
# SOLUTION

spotify_2023_df.drop_duplicates()

```
<img width="862" height="348" alt="Capture" src="https://github.com/user-attachments/assets/57b23174-28a7-4722-9263-22bc96884155" />



- **. Handling Duplicates**:

```python

# re-counting our data point again 
# SOLUTION

len(spotify_2023_df)
# This shows that there was NO duplicates on our dataset

```
<img width="530" height="128" alt="Capture" src="https://github.com/user-attachments/assets/384dc585-a524-4341-8c93-a790b3c4dc6f" />




### **Data Aggregation And Filtering**

```python

# Calculate the total streams for songs released in 2023.

# SOLUTION
# Filter rows where released_year == 2023
spotify_2023_releases = spotify_2023_df[spotify_2023_df["released_year"] == 2023]

# Calculate total streams
total_streams_2023 = spotify_2023_releases["streams"].sum()

print(f"Total streams for songs released in 2023: {total_streams_2023:,}")

```
<img width="425" height="20" alt="Capture" src="https://github.com/user-attachments/assets/0bf4b399-00ee-4b3d-a94a-4111ed188cbb" />




- **. Counting the number of tracks that have over 100 millions streams.**

```python

# Numbers of Tracks that have over 0ne million streams 
# SOLUTION

no_of_tracks_over_1m = spotify_2023_df[spotify_2023_df["streams"] > 100000000]

# # counting the tracks over hundred millions
count_over_100M = no_of_tracks_over_1m["track_name"].shape[0]

print(f" The Total No Of Tracks over Hundred Millions is: {count_over_100M:}")

```
<img width="348" height="25" alt="Capture" src="https://github.com/user-attachments/assets/e2816180-87bf-452a-be51-ab853ff74ed0" />




- **. Finding the average danceability for songs released in 2023.**


```python

# The Average Danceability of songs release in 2023
# SOLUTION

# Condition 1
# filtering the required data
avg_danceability = spotify_2023_df[spotify_2023_df["released_year"] == 2023]

# Condition 2
# Calculating the Averaging danceability
ave_danaceability_of_songs_in_2023 = avg_danceability["danceability_%"].mean().round(5)

# Condition 3
# Getting the Result
print(f" The Average Danceability Of Songs In 2023 is: {ave_danaceability_of_songs_in_2023}")

```
<img width="334" height="24" alt="Capture" src="https://github.com/user-attachments/assets/7fbe7f47-d5f0-4774-9638-8a8544d84f10" />



 - .**Finding the track with the highest number of streams in the dataset.**

```python

# SOLUTION

# Condition 1.
# Filtering the required Columns
spotify_2023_df["streams"] = pd.to_numeric(spotify_2023_df["streams"])

# Findind the row with the highest number of streams
top_track = spotify_2023_df.loc[spotify_2023_df["streams"].idxmax()]

print("The Track with the highest streams is:")
print(top_track[["track_name", "artist(s)_name", "streams"]])

```
<img width="362" height="71" alt="Capture" src="https://github.com/user-attachments/assets/2143457b-29ac-4f61-b7e4-8ff66369e6b6" />



-**.Categorizing songs based on their energy level:**


```python

# Creating a Control Flow formula to categorize songs based on their energy level:
# Define a function using categorize_energy

# SOLUTION
def categorize_energy(energy):
    if energy > 70:
        return "High Energy"
    elif energy >= 40:
        return "Medium Energy"
    else:
        return "Low Energy"

# Applying the function to the dataframe
spotify_2023_df["Energy_Category"] = spotify_2023_df["energy_%"].apply(categorize_energy)

# Check for result result
print(spotify_2023_df[["energy_%", "Energy_Category"]].head(100))

```
<img width="222" height="184" alt="Capture" src="https://github.com/user-attachments/assets/cc3923f1-af0f-4176-a0c6-153d4ebd6e4e" />




- .**Extracting the first and Last 3 characters of Track_name and Artist_name**


```python

# Condition 1
# Extract first 3 characters of track names 
spotify_2023_df["track_first3"] = spotify_2023_df["track_name"].str[:3]

# Condition 2
# Extract last 3 characters of artist names
spotify_2023_df["artist_last3"] = spotify_2023_df["artist(s)_name"].str[-3:]

# Condition 3
# Preview Result
print(spotify_2023_df[["track_name", "track_first3", "artist(s)_name", "artist_last3"]].head(10))

```
<img width="337" height="303" alt="Capture" src="https://github.com/user-attachments/assets/5385feb8-f8f1-4c65-a543-e9605aaed7bd" />




- **.Highlighting Top Tracks With The Highest Streams**

```python

# SOLUTION

# Condition 1
# Highlight top 5 streams
def highlight_top5(val):
    color = "background-color: yellow"
    return color if val in top5_streams else ""

# Find top 5 stream values
top5_streams = spotify_2023_df["streams"].nlargest(5).values

ranking_the_top_streams = spotify_2023_df.style.applymap(
    highlight_top5, subset=["streams"])
ranking_the_top_streams

```
<img width="842" height="349" alt="Capture" src="https://github.com/user-attachments/assets/5025bf7e-24b2-43eb-9031-36d163907c90" />



- **Highlight Tracks with Energy Above 80%**

```python

# highting the track energy above 80%

# SOLUTION
# Condition 1
def highlight_energy(val):
    color = "background-color: Green"
    return color if val > 80 else ""

# Condition 2
spotify_2023_df.style.applymap(
    highlight_energy, subset=["energy_%"]
)

```
<img width="486" height="442" alt="Capture" src="https://github.com/user-attachments/assets/2d6dccf4-f5bd-42ff-8682-17187eec8f04" />



- **.Combining both Rows**


```python

def highlight_rows(row):
    if row["streams"] in top5_streams:
        return ["background-color: yellow"] * len(row)
    elif row["energy_%"] > 80:
        return ["background-color: lightgreen"] * len(row)
    else:
        return [""] * len(row)

spotify_2023_df.style.apply(highlight_rows, axis=1)

```
<img width="885" height="406" alt="Capture" src="https://github.com/user-attachments/assets/cbc1af29-58a6-44c9-83d9-521e5c87b480" />




- **Calculate the overall average stream count for all tracks in the dataset**


```python

# Calculate the overall average stream count

# SOLUTION
average_streams = spotify_2023_df["streams"].mean()

print("Average streams per track:", average_streams)

```
<img width="329" height="18" alt="Capture" src="https://github.com/user-attachments/assets/c74eef74-183f-4111-9b1d-dd265bf76e2a" />


- **Calculate the total number of streams across all tracks in 2023.**

```python

# Total streams across all tracks in 2023

# SOLUTION
total_streams = spotify_2023_df["streams"].sum()

print("Total streams across all tracks in 2023:", total_streams)

```
<img width="367" height="27" alt="Capture" src="https://github.com/user-attachments/assets/5d09d97e-9740-433e-989c-6e2dabf15710" />


- **Count the number of tracks with a BPM between 120 and 140**

```python

tracks_bpm_120_140 = spotify_2023_df[
    (spotify_2023_df["bpm"] >= 120) & (spotify_2023_df["bpm"] <= 140)
].shape[0]

print("Number of tracks with BPM between 120 and 140:", tracks_bpm_120_140)

```
<img width="359" height="23" alt="Capture" src="https://github.com/user-attachments/assets/a0f79826-c6ec-4dc7-9497-17af522bf019" />




### **Summarizing and Visualizing Data:**

```python

avg_energy_by_artist = (
    spotify_2023_df.groupby("artist(s)_name")["energy_%"]
    .mean()
    .sort_values(ascending=False)
)
avg_energy_by_artist.head(10)

```
<img width="291" height="166" alt="Capture" src="https://github.com/user-attachments/assets/d7685c74-af59-404d-9079-f676c8db7543" />

```pyhon
import matplotlib.pyplot as plt

plt.figure(figsize=(8, 6))

avg_energy_by_artist.head(10).plot(kind="bar", color="skyblue")  # show top 10 for clarity

plt.title("Average Energy of Songs by Artist (Top 10)", fontsize=14)
plt.xlabel("Artist", fontsize=12)
plt.ylabel("Average Energy (%)", fontsize=12)
plt.xticks(rotation=75, ha="right")
plt.tight_layout()
plt.show()

```
<img width="521" height="341" alt="Capture" src="https://github.com/user-attachments/assets/9d9e24fc-58dc-48e9-b2fe-93cb43cc105f" />


**Based on my analysis, recommend the top 3 tracks to focus on for future playlists based on
streams and energy levels.Identify the top 3 artists who have the most streamed tracks**

- **.Top 3 Tracks To Focus On (Streams + Energy)**

```python

# Calculate average energy to set a "high energy" threshold
energy_threshold = spotify_2023_df["energy_%"].mean()

# Filter for high energy tracks
high_energy_tracks = spotify_2023_df[spotify_2023_df["energy_%"] > energy_threshold]

# Sorting streams by top 3
top_tracks = high_energy_tracks.sort_values(by="streams", ascending=False).head(3)

print(top_tracks[["track_name", "artist(s)_name", "streams", "energy_%"]])

```
<img width="494" height="141" alt="Capture" src="https://github.com/user-attachments/assets/3976b0da-6f79-49d4-afd2-1d4af126bb7a" />



- **Top 3 artists with the most streamed tracks**

```python

# Group by artist and sum their streams
artist_streams = spotify_2023_df.groupby("artist(s)_name")["streams"].sum()

# Sort and take top 3
top_artists = artist_streams.sort_values(ascending=False).head(3)

print(top_artists)

```
<img width="252" height="82" alt="Capture" src="https://github.com/user-attachments/assets/51fdc0ea-a7e7-4266-b612-7fb8b43a5c85" />




### **Key Findings**
---

#### 1. **Streams**

* The dataset contains tracks with **massive streaming numbers**, some crossing the **hundreds of millions**.
* The **total number of streams across all tracks** is extremely large, showing the dataset is dominated by globally popular hits.
* The **average stream count per track** is high, but only a small percentage of songs cross **100M streams** → meaning success is concentrated among top hits.

---

#### 2. **Release Year 2023**

* Tracks released in **2023 alone** already have huge streaming totals.
* This indicates that **new releases quickly accumulate streams**, reflecting the importance of playlists and promotions on platforms.

---

#### 3. **Tracks & Energy**

* Using our categorization:

  * **High Energy (>70%)** → majority of tracks fall here, especially mainstream pop/EDM.
  * **Medium Energy (40–70%)** → balanced tracks, often ballads or softer pop.
  * **Low Energy (<40%)** → very few tracks, showing listeners favor energetic music.
* High energy tracks (e.g., Olivia Rodrigo’s *“vampire”*, Taylor Swift’s *“Cruel Summer”*) dominate in both streams and popularity.

---

#### 4. **BPM**

* A significant number of tracks have **BPM between 120–140**, the range typical for dance/pop songs.
* This aligns with the observation that **popular tracks lean toward upbeat, danceable tempos**.

---

#### 5. **Top Artists**

* Based on the **grouo_by analysis**:

  * The **Top 3 artists** by total streams are clear leaders (global stars with multiple hits in the dataset).
  * These artists consistently appear across charts and playlists, consolidating their dominance.

---

#### 6. **Top Tracks**

* The **top 3 tracks by streams & energy** are strong candidates for future playlists.
* They are all **high-energy, highly streamed tracks**, which means they resonate with listeners and are playlist-ready.

---

### 7. **Visual Insights**

* The **bar chart of average energy by artist (Top 10)** shows most top-streaming artists maintain **very high energy levels (above 90%)**.
* Adding stream counts above the bars confirmed their dominance.

---


### **Conclusions**

---

From the analysis of the Spotify 2023 dataset, it is evident that **streaming success is concentrated among a small group of highly popular tracks and artists**. The majority of songs with the highest streams are **high-energy** and fall within the **120–140 BPM range**, highlighting that listeners favor upbeat, energetic, and danceable music.

Tracks released in **2023 alone already account for a significant share of streams**, showing how quickly new releases gain traction, largely supported by playlists and strong fan engagement. Meanwhile, only a limited number of tracks achieve more than **100 million streams**, further emphasizing the competitive and hit-driven nature of the music industry.

At the artist level, a few global superstars dominate the charts, consistently producing multiple high-streaming tracks. Their dominance reflects not only musical appeal but also the impact of branding, fanbase strength, and industry influence.

In summary, **high-energy tracks from top global artists drive the majority of streams**, and future playlist strategies should prioritize these songs while still including select medium-energy tracks for variety.

---



### **Reconmendation**
---

1. **Prioritize High-Streaming Tracks**

   * Focus playlists around the top 3 tracks with the highest streams since they already attract the largest audiences.
   * These tracks should be placed at the beginning of playlists to maximize engagement.

2. **Leverage High-Energy Songs (Energy > 70%)**

   * Data shows that high-energy tracks dominate listener preferences.
   * Build playlists around these songs, especially those with BPM between 120–140, as they align with global hit trends.

3. **Feature Top Artists Consistently**

   * The top 3 artists with the most streams should be prioritized in multiple playlists.
   * Collaborations or promotions involving these artists are likely to yield higher engagement.

4. **Balance with Medium-Energy Tracks**

   * While high-energy songs perform best, include some medium-energy tracks (40–70%) for variety.
   * This balance keeps playlists engaging and avoids listener fatigue.

5. **Focus on Recent Releases (2023)**

   * Tracks released in 2023 already contribute heavily to overall streams.
   * Promote these songs in “New Music” or “Trending” playlists to capture current listener demand.

6. **Cross-Platform Opportunities**

   * Since tracks also appear in Apple, Deezer, and Shazam charts, target songs with cross-platform traction for higher playlist impact.

---

👉 In short: **Build playlists around top artists, prioritize high-energy & high-stream tracks, include trending 2023 songs, and balance with mid-energy content for variety.**

---

# **THE END**
