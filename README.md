# XRates

## Website for getting Ukrainian hryvnia exchange rates and converting them to foreign currencies

This project is a secure, scalable, and high-performance website, optimized using the NoSQL database Redis as a cache to handle multiple requests to a third-party API for exchange rates.\
It also provides a convenient currency converter and stores conversion history.

## Features

- Built-in Django authentication
- Integration with third-party API to fetch exchange rates
- Currency converter with conversion history
- Exchange rate caching with Redis

## Installation & Usage (Docker Compose)

### 1. Clone the reposity

```
git clone https://github.com/whales-dmtr/xrates.git
cd xrates
```

### 2. Run with Docker Compose

```
docker compose up
```

## Access the Website

After running the project (e.g., with Docker Compose or `manage.py runserver`), open your browser and go to:

\*\*[http://localhost:8080/\*\*](http://localhost:8080/**?utm_source=chatgpt.com)

This is the default URL where the site will be accessible locally.

If you run the app in Docker and mapped ports differently, adjust the URL accordingly.

## Tech Stack

- Backend: Python, Django
- Database: PostgreSQL
- Cache: Redis
- Containerization: Docker & Docker Compose

## Development

```
# This project requires Python 3.13.5
# You can install it from the official Python website
# or using pyenv:
pyenv install 3.13.5

# Start the database
# The easiest way is to use Docker:
docker run --name xrates-db -e POSTGRES_PASSWORD=postgres -e POSTGRES_DB=xrates -d -p 5432:5432 postgres

# If you don't have Docker installed,
# you'll need to install PostgreSQL manually and create the database

# Start the Redis server 
# Again, you can run it with Docker or manually:
docker run --name xrates-cache -d -p 6379:6379 redis

# Create a .env file
# Make sure you're in the root directory of the project

# If you used the Docker command above,
# you can simply copy the .env file mentioned in the Installation section,
# but you need to change DJANGO_DEBUG to 1 (for development mode)

# If you created the database manually or run the Redis server manually,
# copy the template from .env.example, fill in the values, and continue

# Create and activate a virtual environment
python3.13 -m venv venv
source venv/bin/activate

# Install dependencies
python3.13 -m pip install -r requirements.txt

# Start the application
python3 xrates/manage.py runserver
```

## License

MIT — do whatever you want but don’t blame me :)
