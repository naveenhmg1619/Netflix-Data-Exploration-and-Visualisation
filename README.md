# Netflix Data Analysis Project

## About Netflix

Netflix is a leading media streaming service offering a vast library of movies and TV shows. With over 10,000 titles and 222 million subscribers worldwide as of mid-2021, Netflix continues to be a dominant player in the entertainment industry.

## Business Problem

The goal of this project is to analyze Netflix's extensive dataset to uncover insights that could guide the company's content strategy and expansion plans across different markets.

## Skills Utilized
- Data Cleaning
- Exploratory Data Analysis
- Pandas, NumPy, Matplotlib, Seaborn
- Data Visualization
- Python Programming

## Dataset

The dataset includes details such as cast, directors, ratings, release year, and duration for all titles available on Netflix.

### Data Attributes

- **Show_id**: Unique identifier for each title
- **Type**: Distinguishes between movies and TV shows
- **Title**: Name of the title
- **Director**: Director of the title
- **Cast**: Actors involved
- **Country**: Production country
- **Date_added**: Date added to Netflix
- **Release_year**: Year of release
- **Rating**: Content rating
- **Duration**: Length in minutes or seasons
- **Listed_in**: Genre categories
- **Description**: Brief summary

## Analysis Objectives

- Determine the types of content prevalent in different regions.
- Track the evolution of content releases over the past decades.
- Compare the prevalence of TV shows versus movies.
- Identify optimal release timing for new shows.
- Analyze the impact of actors and directors on content success.
- Assess Netflix's focus shift between TV shows and movies.
- Understand regional content availability.

## Problems and Solutions

### 1. Inconsistent Data Types
- **Problem:** 'date_added' column was not in datetime format, and 'duration' had mixed formats.
- **Solution:** Converted 'date_added' to datetime and standardized 'duration' to minutes.
- **Method:** Used `pd.to_datetime()` and a custom function `convert_duration_to_min()`.

### 2. Missing Values
- **Problem:** Rows with missing 'date_added', 'rating', and 'duration' values.
- **Solution:** Dropped rows with missing values.
- **Method:** Applied `data.dropna(subset=[column_name], inplace=True)`.

### 3. Incorrect Data Entries
- **Problem:** 'rating' entries mistakenly entered as durations in minutes.
- **Solution:** Removed incorrect 'rating' entries.
- **Method:** Utilized `data.drop(data[data['rating'].isin([incorrect_values])].index, inplace=True)`.

### 4. Mixed Data Formats
- **Problem:** Multi-valued columns like 'genre', 'director', 'cast', and 'country' had mixed formats.
- **Solution:** Split and exploded these columns into individual rows.
- **Method:** Employed `str.split()` and `explode()`.

### 5. Redundant Columns
- **Problem:** Unnecessary columns present in the dataset.
- **Solution:** Dropped unwanted columns to streamline the dataset.
- **Method:** Used `data.drop(columns=[list_of_columns], inplace=True)`.

## Visualization Summary

- **Data Visualization:** Utilized Matplotlib and Seaborn libraries to create a variety of charts and graphs that illustrate the distribution and counts of various categories within the Netflix dataset. This included bar charts, pie charts, histograms and Scatter plots to effectively communicate the insights derived from the data.

**For detailed visual examples, please refer to the Jupyter notebooks in this repository.**

# Recommendations for Netflix Content Strategy

1. **Diversify TV Show Offerings**: Currently, TV shows represent only 30% of content. To enhance variety, it's recommended to increase the number of TV shows, particularly from underrepresented time periods, to create a more comprehensive catalog.

2. **Expand Family-Friendly Content**: There is an opportunity to grow the collection of TV shows with ratings like TV-G, TV-Y, TV-Y7, and movies rated PG, NR, G. These categories are currently underrepresented compared to the top-rated shows and could attract a broader audience.

3. **Focus on High-Population Markets**: India and China, with their vast populations, present significant growth opportunities. Increasing the number of shows and producing more local content in India could elevate its position in the market. Additionally, catering to the growing preference for multi-season TV shows could engage viewers more deeply.

4. **Target Genre-Specific Audiences**: South Korean and Japanese movies have a dedicated fanbase. By promoting these genres to viewers who enjoy South Korean and Japanese dramas, Netflix can capitalize on this existing popularity.

5. **Localize Content Promotion**: Dramas, documentaries, and comedies enjoy high viewership but are popular in specific countries. Tailoring promotions to align with the tastes of each country can increase the relevance and appeal of these genres.

6. **Address Declining New Releases**: The addition of new movies has slowed since 2019. To maintain viewer interest, Netflix should consider producing more original content, thereby enriching the platform's offerings.

7. **Consistency in Content Updates**: The current trend indicates inconsistency in the frequency of content updates. Establishing a regular schedule for adding shows can help manage viewer expectations and maintain a steady flow of new content.

8. **Promote Emerging Genres**: Anime has shown an uptick in popularity among less favored genres. A focused promotional effort could further boost viewership for anime content.

9. **Timely Content Addition**: Over half of the shows are added to the platform more than a year after release. To capture viewer interest, it's advisable to add shows within the same release year, leveraging the momentum of new content.

