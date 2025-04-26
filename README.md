# 🎶 Telugu Music Playlist Analysis

![Project Banner](https://github.com/user-attachments/assets/a77328c6-7073-483b-bae0-fc15e093d105)


A mini data analytics project exploring 100 Telugu movie songs using **SQL** and **Excel**. Analyzed trends like songs per movie, year, and director, uncovering insights into Telugu cinema's musical landscape. 

## 📊 Project Goals
- Build a SQL database to store song metadata (title, artist, movie, year).
- Analyze trends with SQL JOIN queries (e.g., songs per director).
- Visualize insights with Excel charts to tell a story about Telugu music.

## 🛠️ Technologies Used
- **SQL**: DB Fiddle for database creation and querying.
- **Excel**: Pivot Tables and bar charts for analysis and visualization.
- **GitHub**: Version control and project hosting.

## 📈 Dataset
- **Source**: Manually compiled 100 Telugu songs from movies like *Arya 2*, *Devara Part 1*, and *Ye Maaya Chesave*.
- **Structure**:
  - `TeluguSongs`: SongID, SongTitle, Artist, Movie, YearReleased.
  - `Movies`: MovieName, Director, Genre, BoxOfficeRevenue.
- **Size**: 100 songs, 14 movies, spanning 2002-2024.

## 📖 Data Dictionary
### TeluguSongs Table
- `SongID`: Unique identifier for each song (Integer).
- `SongTitle`: Name of the song (VARCHAR).
- `Artist`: Performing artist(s) (VARCHAR).
- `Movie`: Movie the song belongs to (VARCHAR).
- `YearReleased`: Release year of the movie (Integer).

### Movies Table
- `MovieName`: Name of the movie (VARCHAR, Primary Key).
- `Director`: Director of the movie (VARCHAR).
- `Genre`: Movie genre (e.g., Romance, Action) (VARCHAR).
- `BoxOfficeRevenue`: Box office revenue in millions INR (Integer).

## 🔍 Project Steps
1. **Data Creation**:
   - Created `TeluguSongs` and `Movies` tables in DB Fiddle.
   - Example SQL:
     ```sql
     CREATE TABLE TeluguSongs (
         SongID INTEGER PRIMARY KEY,
         SongTitle VARCHAR(100),
         Artist VARCHAR(100),
         Movie VARCHAR(100),
         YearReleased INTEGER
     );

     CREATE TABLE Movies (
         MovieName VARCHAR(100) PRIMARY KEY,
         Director VARCHAR(100),
         Genre VARCHAR(50),
         BoxOfficeRevenue INTEGER
     );
     ```
2. **Analysis**:
   - Used SQL JOINs to analyze songs per director and genre.
   - Example Query:
     ```sql
     SELECT m.Director, COUNT(s.SongID) AS SongCount
     FROM TeluguSongs s
     JOIN Movies m ON s.Movie = m.MovieName
     GROUP BY m.Director
     ORDER BY SongCount DESC;
     ```
3. **Visualization**:
   - Built Excel charts: Songs per Movie, Songs by Year, Box Office Trends.
   - Songs per Movie![songs_per_movie](https://github.com/user-attachments/assets/746390ae-ec93-47fd-a7d4-a7a5d6e87f27)


   - Songs by year![songs_per_year](https://github.com/user-attachments/assets/57b3b8f3-73dc-4327-a6f1-07d66f460ab8)

   - Box Office Revenue![box_office_revenue](https://github.com/user-attachments/assets/5e107f9c-e9ae-4028-b621-0ade36371eff)


## 💡 Key Insights
- **Top Movies**: *Arya 2*, *Darling*, and *Devara Part 1* lead with 14 songs each.
- **Director Trends**: Sukumar has the most songs (28), followed by S.S. Rajamouli (16).
- **Genre Insights**: Romance movies dominate with 35 songs, reflecting a musical trend.

## 🛡️ Challenges and Solutions
- **Challenge**: Filtering top 10 movies in Excel Pivot Table included ties (e.g., 7 movies with 14 songs).
- **Solution**: Manually adjusted filters to limit to 10 rows, ensuring clarity in visualizations.
- **Challenge**: Total song count was initially 96 instead of 100.
- **Solution**: Removed duplicates in Excel and re-exported data from DB Fiddle.

## 📂 Files
- `telugu_music_playlist.sql`: SQL code for database creation.
- `telugu_music_data_100.xlsx`: Excel file with raw data and charts.
- `output/`:
  - `songs_per_movie_top10.png`
  - `songs_per_year_top10.png`
  - `box_office_revenue.png`
  - `project_banner.png`

## 🚀 How to Run
1. Open `telugu_music_playlist.sql` in DB Fiddle (MySQL 5.7 or SQLite).
2. Run the SQL to create tables and insert data.
3. Export results to Excel and explore `telugu_music_data_100.xlsx`.

## 🌟 Future Improvements
- Expand the dataset with more songs and metrics (e.g., song duration).
- Create an interactive dashboard with Power BI (planned for a future project).
- Add statistical analysis using Python or R.

## 📬 Get in Touch
Loved this project? Let’s connect on LinkedIn: www.linkedin.com/in/saipriyakakarla ! I’d love to hear your feedback or discuss data analytics opportunities.
