# Databricks ETL
This project it`s an elt using as data source the spotify api, the documentation can be found [here](https://developer.spotify.com/documentation/web-api).

### Technologis
The followig tools were used for the development:

- Python
- Spark
- Pyspark
- Databricks
- Sql

## Api
It is necessary to register in the spotify for developers to create an app to get the credentials client_id and client_secret, for post and get requests.
The secrets were set on the cluster enviroment variables. To get the token, it is necessary a post request with b64 encode, then get the bearer token. The token expires in one hour.
The function 'get_artist' get the artist id to use in another function to get the top tracks by artist id.

## Data
To treat the data, explored to see how it is, used trim for string and cast int for numbers and date for date, then add a load date, saved as delta and create the table in the metastore using the delta location. A function 'insert_sql_table' inserts the data in azure sql, that can be consumed by power by, for example. It`s to run the upsert after the first load. 
