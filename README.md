# 📒 Data Modelling in Apache Cassandra


This project is part of the Udacity Nanodegree® on Data Engineering. 

It aims to demonstrate database creation from a JSON store by creating appropriate database structures and populating correct data post ETL.

> 🧘🏽 “Data that is loved tends to survive.” - _Kurt Bollacker_

## Core Technologies
![Shield](https://img.shields.io/badge/Database-ApacheCassandra-lightgrey) 
![Shield](https://img.shields.io/badge/Language-Python|CQL-lightgrey)
![Shield](https://img.shields.io/badge/RawData-CSV-lightgrey)
## Usage

Execute the file using,
```bash
python etl.py
```

The data will then be loaded to the tables created and can be tested using the ```test.ipynb``` notebook present in the repository.

## Database Architecture

![A](https://github.com/asonthalia/Sparkify-Data-Modelling-With-Postgres/blob/472ebd15c8991b3b680bec178fd69b2dd728eb88/Images/Architecture%20copy.png)
Created using [Creatly](https://app.creately.com). Sorry for the attribute stacking in the ```SONGPLAYS``` table, creately only allows for 60 elements in their free version!

The schema followed for this database is a [star schema](https://en.wikipedia.org/wiki/Star_schema).

```ARTIST_ID``` is a duplicate column in ```SONGS``` and ```ARTISTS```; this makes a more read oriented structure that is always prefered in analytics. Since the objective is to optimise analytical workflow, this structure supports our goal.

All tables have been ensured to have a ```PRIMARY KEY```.
Column datatypes and sizes have been marked as per observed business data.
```LATITUDE``` and ```LONGITUDE``` have been capped till 5 digits accuracy after the decimal point to ensure ```~cm accuracy```. ([Source](https://rapidlasso.com/2019/05/06/how-many-decimal-digits-for-storing-longitude-latitude/)) 

## File Dictionary
- ```create_tables.py``` - Helps in resetting/ creating the database and the tables within.
- ```sql_queries.py``` - Queries to support resetting/ creating/ dropping and 'upsertion' of tables and data.
-  ```etl.py``` - Performs the reading of JSON files, type conversions where necessary and pumping into Postgres.
-  ```etl.ipynb``` - Interactive version of etl.py
- ```test.ipynb``` - Notebook to check if the data was correctly loaded.

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)

