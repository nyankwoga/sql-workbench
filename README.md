# sql-workbench


### Difficulties
1. **OCR Accuracy**: Extracting text from an image using OCR can be challenging, especially if the image quality is not optimal. This often results in incorrect or incomplete data extraction.
2. **Data Cleaning**: The dataset has redundant entries (e.g., 'Fashion' appears twice for Jesse Lawhorn), which requires cleaning to ensure data quality.
3. **Special Characters**: Non-standard characters or diacritics in place names (e.g., "Al Abyār") can cause issues with encoding and require additional handling to ensure they are correctly represented.

### Interesting Thing
An interesting observation about this dataset is the diversity in user interests and geographic locations. Despite being a small dataset, it spans multiple continents and a wide range of hobbies and professional interests. This could provide valuable insights into cultural and demographic patterns when analyzing user preferences and activities.



### 2. Data Fun

Let's explore the dataset using SQL queries to find interesting facts:

1. **Most Popular Interests:**

   ```sql
   SELECT Interests, COUNT(*) AS Count
   FROM table_name
   GROUP BY Interests
   ORDER BY Count DESC;
   ```

   This query will show us the interests that appear most frequently across all users.

2. **Average Age of Users:**

   Given the DOB column, we can calculate the average age of users.

   ```sql
   SELECT AVG(YEAR(NOW()) - YEAR(STR_TO_DATE(DOB, '%d/%m/%Y'))) AS AverageAge
   FROM table_name;
   ```

   This query calculates the average age of users based on their date of birth.

### 3. Ask Away

Let's formulate and answer two questions about the data:

1. **Question 1: What are the most popular interests among users in Indonesia?**

   ```sql
   SELECT Interests, COUNT(*) AS Count
   FROM table_name
   WHERE Country = 'Indonesia'
   GROUP BY Interests
   ORDER BY Count DESC;
   ```

   **Answer 1:** From the query, we can learn about the specific interests that are most popular among users in Indonesia.

2. **Question 2: What is the distribution of genders among users interested in 'Fashion'?**

   ```sql
   SELECT Gender, COUNT(*) AS Count
   FROM table_name
   WHERE Interests LIKE '%Fashion%'
   GROUP BY Gender;
   ```

   **Answer 2:** This query will provide insights into how many males and females have listed 'Fashion' as one of their interests.

### Insights from the Data

- **Popular Interests:** By analyzing the results of the first SQL query (`Most Popular Interests`), we can identify which interests are most prevalent among the users. This can help in understanding the general preferences and hobbies of the dataset population.
  
- **Average Age:** The average age query (`Average Age of Users`) gives us a sense of the age demographic of the users. This could be useful for targeted marketing or understanding age-related trends in interests.

- **Regional Insights:** The queries under `Ask Away` (e.g., popular interests in Indonesia, gender distribution in 'Fashion') allow us to derive regional and interest-specific insights. This helps in understanding cultural and gender-related preferences within the dataset.

By leveraging SQL queries, we can uncover valuable insights about the dataset, ranging from popular interests to demographic distributions, enabling better decision-making and understanding of the dataset characteristics.