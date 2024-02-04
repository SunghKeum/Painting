<h1>Painting (SQL Project)</h1>

<h2>📝 Project Description</h2>https://github.com/SunghKeum/Painting/blob/main/README.md

In this SQL project, I use Python packages (psycopg2, pandas, and sqlalchemy) under Jupyter Notebook environment to upload data from CSV files to PostgreSQL database tables. After import, I use SQL queries to answer several questions related to the famous paintings dataset. You can view the data used for this project [here](https://www.kaggle.com/datasets/mexwell/famous-paintings).

<h2>🛠 Skills Acquired and Gained</h2>

- Connecting Python to PostgreSQL Database Server
- JOIN
- UNION
- SUBQUERY
- CTE
- Window Functions (DENSE_RANK() & ROW_NUMBER())
- Partitioning

<h2>Uploading CSV files to PostgreSQL database using Python scripts</h2>

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
  <img width="1000" height="400" src="/Painting/Question 1.png">
</p>



