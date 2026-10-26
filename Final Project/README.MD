<h1 align = 'center'> <b> Netflix Movie & TV Show Duration Over Time </b></h1>

<h3 align= 'center'> Problem Statement </h3>
Netflix is a popular media and video streaming platform. The platform is home to over a combined 8,000 movies and TV shows, video games on mobile devices based on their properties, and has a global audience of over 200 million subscribers. With this data set, I wanted to see two things.

<br> 1. The distribution of movies and TV Shows. Which type of entertainment dominates the platform and by how much?
<br> 2. How the duration of movies and TV Shows change over time.

<h3 align= 'center'> Data Dictionary </h3>
Listings of all the movies and TV shows available on Netflix as of 2021. Created by Shivam Bansai on Kaggle (https://www.kaggle.com/datasets/shivamb/netflix-shows).

<br> Columns (12):
<br> show id - Unique ID for every show/movie (string)
<br> type - Identifier - a movie or TV show (string)
<br> title - Title of the show/movie (string)
<br> director - Director of the show/movie (string); NOTE: missing 2,634 values
<br> cast - Actors involved in the show/movie (string); NOTE: missing 825 values
<br> country - Country where the show/movie was produced (string); NOTE: missing 831 values
<br> date added - Date the show/movie was added on Netflix (string); NOTE: says it is formatted as a date on Kaggle but but upon importing, it's stored as a string; Missing 10 values
<br> release year - Release year of the show/movie (integer)
<br> rating - TV Rating of the show/movie (string); NOTE: missing 4 values
<br> duration - Duration in minutes or number of seasons (string); NOTE: 3 values
<br> listed in - Genre of the show/movie (string)
<br> description - Description of the show/movie (string)

<br>Expected after cleaning: 8790 rows and 15 columns (4,300 rows replaced or removed), 831 values in country column replaced (mode-imputed), 3,459 missing values from the director, cast columns were replaced ('None Stated'), 10 rows dropped, date added column formatted to datetime, 3 new columns named month num added, month name added, and year added created.

<h3 align= 'center'> Cleaning Steps </h3>
1. Replacing values
  <br> Overall, there were 4,307 missing values in the data. I decided to keep the country, director, and cast columns as that might be useful data. I replaced the missing values in the country column with the most common country in the data, which happened to be the United States. Next, I replaced the director and cast columns with "None Stated", while we will not use these columns for this project, it's important to preserve them because they account for approximately 39% of the data. Removing missing values within these columns would, effectively, butcher my data.

<br> 2. Removing values
  <br> I dropped the 10 missing values from the date added column, Realistically, there wasn't a viable way for me to replace the data points and since it was such a small size, it make sense to remove them.

<br> 3. Duplicates
  <br> There isn't any duplicate values in the data!

<br> 4. Changing data types
  <br> The date added was stored as a string (or object) type, which means it needed to be changed. Additionally, there were rows that had trailing and leading spaces within the column. This column needed to be cleaned because it is the basis of my analysis, and needed to be formatted correctly. All trailing and leading spaces were removed and the dates were formatted into numeric forms of month - day - year.

<br> 5. Adding columns
  <br> I added month_num_added (the month added as a number), month_name_added (the month in string format), and year_added columns to have an easier breakdown of change over time and to have a more in depth analysis if needed.

<h3 align= 'center'> Findings </h3>

<br><b> 1. Movies are the most dominant type on the platform (69%). </b>
  <br> From the 8790 rows of cleaned data I was able to determine 6,131 movies were listed on Netflix while only 2,676 TV shows were available on the platform. This means that movies make up approximately 69.62% of entertainment options on Netflix while TV shows only make up approximately 30.38%. 
  
  <br><img src='https://github.com/miyahjordan/cs82a-portfolio/blob/main/Final%20Project/Visualizations/Movie%20v.%20TV%20shows%20Composition.png?raw=true' />

<br><b> 2. Average movie lengths have increased since 2012. </b>
  <br> Solely looking at movie lengths, we can see that the lengths fluctuate over time, with 2012 being the lowest. Since then, watch times are been increasing, with a peak in length in 2018.
  
  <br><img src='https://github.com/miyahjordan/cs82a-portfolio/blob/main/Final%20Project/Visualizations/Movie%20Length%20Over%20Time.png?raw=true' />

<br><b> 3. TV Show lengths haven't been able to return to their peak in 2014. </b>
  <br> From 2008 to 2013, the average length for a TV show was steadily increasing, and even hit a peak in 2014. However, there was a sharp decline in 2015 - 2016, with 2016 being the lowest. From 2017 onward, the average length of TV shows do not seem to go past 2 seasons.
  
  <br><img src='https://github.com/miyahjordan/cs82a-portfolio/blob/main/Final%20Project/Visualizations/TV%20Show%20Length%20Over%20Time.png?raw=true' />

<br><b> 4. Movies are being produced more than TV Shows. </b>
  <br> With the dual line plot, we can see that the count of movies have drastically increased over time with a peak of around 1,400 movies on the platform in 2019. In comparison, TV shows have not been added as much, with their peak being around 2019 - 2020. It's important to note that after 2020, the production of both entertainment types drop, more than likely due to COVID.
  
  <br><img src='https://github.com/miyahjordan/cs82a-portfolio/blob/main/Final%20Project/Visualizations/Movies%20&%20Tv%20Shows%20Over%20Time.png?raw=true' />

<h3 align= 'center'> So What? </h3>
From the information I gathered, we can clearly see movies are getting pushed out on the platform more than TV shows. With such a high focus on producing movies instead of TV shows, I think that majority of Netflix subscribers gravitate to their movies more than their shows. Since TV show lengths have not pushed past 2 seasons since 2017 and there only seems to be a slight increase in production since then, I theorize that the length of these shows contribute to the lack of retention. However, without retention data, I cannot be certain that this is the case.
