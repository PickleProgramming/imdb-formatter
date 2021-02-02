# imdb-formatter
SQLAlchemy script that takes the IMDb datasets and puts them in a pretty format.

After setting up a PostgreSQL server I used the [IMDbPy](https://imdbpy.readthedocs.io/en/latest/usage/s3.html) package to import the raw TSV's from IMDb into the database. After which I wrote this script to put all that data into 2 nice human readable tables: one for TV series, and one for movies. Examples:

| tconst  | title | year | runtime | director | writer | starring | genres | rating | votes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 001 | 2001: A Space Odyssey | 1969 | 120 | Stanley Kubrick | Stanely Kubrick, Arthur C. Clarke | People,People,HAL | Sci Fi, Adventure | 10 | 1000000 |

| tconst  | title | start year | end year | episode runtime | creator | starring | genres | rating | votes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 001 | Mr. Robot | 2014 | 2019 | 49 | Sam Esmail | Rami Malek,Christian Slater,Martin Walstrom | Thriller,Mystery | 10 | 10000000 |

The script filters out any shorts, video games, TV specials, TV movies, adult content, and any entries that are incomplete; i.e. any entries that don't have *all* of the fields listed above.
Eventually I plan on automating the script to run maybe once a month and upate the table with any new entries.
