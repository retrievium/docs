# Running gulper-v1 locally

Data ingestion worker to populate the databases.

## Setup

```sh
cd gulper-v1
```

### Required dependencies

- [Python 3.9+](https://www.python.org/)
- `pg_config`

#### Installing `pg_config`

On Ubuntu, simply run `sudo apt install libpq-dev`, as see [this StackOverflow post](https://stackoverflow.com/questions/11618898/pg-config-executable-not-found).

### Create and enter virtual environment

https://docs.python.org/3/tutorial/venv.html

```sh
python -m venv venv # make sure not python2, or python less than 3.9!
. ./venv/bin/activate # or something similar to your system
pip install -r requirements.txt
```

### Ensure install works

```sh
python cli.py # should show cli tool help, without errors
```

## Populating the databases with sample data

```sh
python cli.py uploadsampletar # upload sample tar to minio
python cli.py listjobs # should show the job just added
python cli.py queuejobs # queue jobs in faktory for processing
python gulper.py # run the worker to process said jobs
```
