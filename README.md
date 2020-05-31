# SimpleMQ: Lightweight Message Queue

Simple message queue written in Python, using Flask

## Instructions

### Environments

- Python 3.8.1
- Flask 1.1.2

### Make python venv and activate

```bash
# Windows - Git Bash
python -m venv venv
source ./venv/Scripts/activate

# Mac
python3 -m venv venv
source ./venv/bin/activate
```

### Install requirements

```bash
pip install -r requirements.txt
```

### Run Development Server using flask and gunicorn

```bash
chmod 744 ./start
./start
```

### Run Development Server using flask

```
export FLASK_APP=message.py
flask run
```

### Build Docker image and run with Docker CLI

```bash
docker build -t simplemq:0.1 .
docker run --env-file ./.env -p 8000:8000 simplemq:0.1
```

## API

GET `/{prefix}/status`

```
200 'good'
```

POST `/{prefix}`

```
200 'Done'
```

DELETE `/{prefix}`

```
200 [number of lines]
```


## Etc

### `.env` file example

```
FILE_PATH=data/queue
ROUTES=message/
```
