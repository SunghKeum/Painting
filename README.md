<h1>Painting (SQL Project)</h1>

<h2>📝 Project Description</h2>

In this SQL project, I use Python packages (psycopg2, pandas, and sqlalchemy) under Jupyter Notebook environment to upload data from CSV files to PostgreSQL database tables. After import, I use SQL queries to answer several questions related to the famous paintings dataset. You can view the data used for this project [here](https://www.kaggle.com/datasets/mexwell/famous-paintings).

<h2>🛠 Skills Acquired and Honed</h2>

- Connecting Python to PostgreSQL Database Server
- JOIN
- UNION
- SUBQUERY
- CTE
- Window Functions (DENSE_RANK() & ROW_NUMBER())
- Partitioning

<h2>📥 Uploading CSV files to PostgreSQL database using Python scripts</h2>

```
import psycopg2
import pandas as pd
import sqlalchemy as db

engine = db.create_engine('postgresql://postgres:3131@localhost:5433/painting')

conn = engine.connect()

files = ['artist','canvas_size','image_link','museum','museum_hours','product_size','subject','work']

for file in files:
    df = pd.read_csv(f'C:\\Users\\sungh\\OneDrive\\Desktop\\archive\\{file}.csv')
    df.to_sql(file, con=conn, if_exists='replace', index=False)
```
<h2>Question 1: Retrieve all the paintings which are not displayed on any museums</h2>
<p align="center">
  <img width="1000" height="1000" src="/Painting/Question 1.png">
</p>

<h2>Question 2: Are there museums without any paintings?</h2>
<p align="center">
  <img width="1000" height="1000" src="/Painting/Question 2.png">
</p>

<h2>Question 3: How many paintings have an asking price of more than their regular price?</h2>
<p align="center">
  <img width="1000" height="1000" src="/Painting/Q3.png">
</p>

<h2>Question 4: Identify the paintings whose asking price is less than 50% of its regular price</h2>
<p align="center">
  <img width="1000" height="1000" src="/Painting/Q4.png">
</p>

<h2>Question 5: Delete duplicate records from work and product_size tables</h2>
<p align="center">
  <img width="1000" height="1000" src="/Painting/Q5.png">
</p>

<h2>Question 6: Retrieve the top 10 most famous painting subject</h2>
<p align="center">
  <img width="1000" height="1000" src="/Painting/Q6.png">
</p>

<h2>Question 7: Identify the museums which are open on both Sunday and Monday. Display the museum name and city</h2>
<p align="center">
  <img width="1000" height="1000" src="/Painting/Q7.png">
</p>

<h2>Question 8: How many museums are open every single day?</h2>
<p align="center">
  <img width="1000" height="1000" src="/Painting/Q8.png">
</p>

<h2>Question 9: Which are the top 5 most popular museum? (Popularity is defined based on most number of paintings in a museum)</h2>
<p align="center">
  <img width="1000" height="1000" src="/Painting/Q9.png">
</p>

<h2>Question 10: Who are the top 5 most popular artist? (Popularity is defined based on most no. of paintings done by an artist)</h2>
<p align="center">
  <img width="1000" height="1000" src="/Painting/Q10.png">
</p>

<h2>Question 11: Which museum has the most number of popular painting style?</h2>
<p align="center">
  <img width="1000" height="1000" src="/Painting/Q11.png">
</p>

<h2>Question 12: Identify the artists whose paintings are displayed in multiple countries</h2>
<p align="center">
  <img width="1000" height="1000" src="/Painting/Q12.png">
</p>

<h2>Question 13: Which country has the 5th highest number of paintings</h2>
<p align="center">
  <img width="1000" height="1000" src="/Painting/Q13.png">
</p>

<h2>Question 14: Which are the 3 most popular and 3 least popular painting styles?</h2>
<p align="center">
  <img width="1000" height="1000" src="/Painting/Q14.png">
</p>

<h2>Question 15: Which artist has the most number of Portraits paintings outside USA? Display artist name, number of paintings, and the artist nationality.</h2>
<p align="center">
  <img width="1000" height="1000" src="/Painting/Q15.png">
</p>


