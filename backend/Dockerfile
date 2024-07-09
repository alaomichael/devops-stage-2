# # Use an official Python runtime as a parent image
# FROM python:3.10-slim

# # Set the working directory in the container
# WORKDIR /app

# # Install Node.js, npm, and curl
# RUN apt-get update && apt-get install -y \
#     nodejs \
#     npm \
#     curl

# # Install Poetry
# RUN curl -sSL https://install.python-poetry.org | python3 -

# # Add Poetry to PATH
# ENV PATH="/root/.local/bin:$PATH"

# ENV POETRY_HOME="/opt/poetry" \
#     PYSETUP_PATH="/app" \
#     PIP_NO_CACHE_DIR=off \
#     POETRY_VIRTUALENVS_PATH="/app/.venv"

# # Copy the pyproject.toml and poetry.lock files
# COPY pyproject.toml poetry.lock ./

# # Disable virtual envs
# RUN poetry config virtualenvs.create false

# # Install dependencies
# RUN poetry install --no-root

# # Copy the rest of the application code into the container
# COPY . .

# # Give execute permissions to prestart.sh
# RUN chmod +x prestart.sh

# # Expose the port that the app runs on
# EXPOSE 8000

# # Command to run the prestart script and then start the backend server
# CMD ["bash", "-c", "poetry run bash ./prestart.sh && poetry run uvicorn app.main:app --host 0.0.0.0 --port 8000 --reload"]


# # Use an official Python runtime as a parent image
# FROM python:3.10-slim

# # Set the working directory in the container
# WORKDIR /app

# # Install Node.js, npm, curl, and dos2unix
# RUN apt-get update && apt-get install -y \
#     curl \
#     dos2unix

# # Install Poetry
# RUN curl -sSL https://install.python-poetry.org | python3 -

# # Add Poetry to PATH
# ENV PATH="/root/.local/bin:$PATH"

# ENV POETRY_HOME="/opt/poetry" \
#     PYSETUP_PATH="/app" \
#     PIP_NO_CACHE_DIR=off \
#     POETRY_VIRTUALENVS_PATH="/app/.venv"

# # Copy the pyproject.toml and poetry.lock files
# COPY pyproject.toml poetry.lock ./

# # Disable virtual envs
# RUN poetry config virtualenvs.create false

# # Install dependencies
# RUN poetry install --no-root

# # Copy the rest of the application code into the container
# COPY . .

# # Set PYTHONPATH
# ENV PYTHONPATH=/app

# # Give execute permissions to prestart.sh and convert to Unix line endings
# RUN chmod +x prestart.sh && dos2unix prestart.sh

# # Expose the port that the app runs on
# EXPOSE 8000

# # Command to run the prestart script and then start the backend server
# CMD ["bash", "-c", "poetry run bash ./prestart.sh && poetry run uvicorn app.main:app --host 0.0.0.0 --port 8000 --reload"]



# # Use an official Python runtime as a parent image
# FROM python:3.10-slim

# # Set the working directory in the container
# WORKDIR /app

# # Install Node.js, npm, curl, and dos2unix
# RUN apt-get update && apt-get install -y curl \
#     dos2unix

# # Install Poetry
# RUN curl -sSL https://install.python-poetry.org | python3 -

# # Add Poetry to PATH
# ENV PATH="/root/.local/bin:$PATH"

# ENV POETRY_HOME="/opt/poetry" \
#     PYSETUP_PATH="/app" \
#     PIP_NO_CACHE_DIR=off \
#     POETRY_VIRTUALENVS_PATH="/app/.venv"

# # Copy the pyproject.toml and poetry.lock files
# COPY pyproject.toml poetry.lock ./

# # Disable virtual envs
# RUN poetry config virtualenvs.create false

# # Install dependencies
# RUN poetry install --no-root

# # Copy the rest of the application code into the container
# COPY . .

# # Give execute permissions to prestart.sh and convert to Unix line endings
# RUN chmod +x prestart.sh && dos2unix prestart.sh && poetry run bash ./prestart.sh

# # Expose the port that the app runs on
# EXPOSE 8000

# # Command to run the prestart script and then start the backend server
# # CMD ["bash", "-c", "poetry run bash ./prestart.sh && poetry run uvicorn app.main:app --host 0.0.0.0 --port 8000 --reload"]
# CMD ["poetry", "run", "uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000" , "--reload"]


# Use an official Python runtime as a parent image
# FROM python:3.10-slim

# # Set the working directory in the container
# WORKDIR /app

# # Install curl
# RUN apt-get update && apt-get install -y curl

# # Install Poetry
# RUN curl -sSL https://install.python-poetry.org | python3 -

# # Add Poetry to PATH
# ENV PATH="/root/.local/bin:$PATH"

# # Copy the pyproject.toml and poetry.lock files
# COPY pyproject.toml poetry.lock ./

# # Install dependencies
# RUN poetry install --no-root

# # Copy the rest of the application code into the container
# COPY . .

# # Expose the port that the app runs on
# EXPOSE 8000

# # Command to run the backend server
# CMD ["poetry", "run", "uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000" , "--reload"]

# Use an official Python runtime as a parent image
FROM python:3.10-slim

# Set the working directory in the container
WORKDIR /app

# Install required packages
RUN apt-get update && apt-get install -y curl dos2unix

# Install Poetry
RUN curl -sSL https://install.python-poetry.org | python3 -

# Add Poetry to PATH
ENV PATH="/root/.local/bin:$PATH"

# Set environment variables for Poetry
ENV POETRY_HOME="/opt/poetry" \
    PYSETUP_PATH="/app" \
    PIP_NO_CACHE_DIR=off \
    POETRY_VIRTUALENVS_PATH="/app/.venv"

# Copy the pyproject.toml and poetry.lock files
COPY pyproject.toml poetry.lock ./

# Disable Poetry's virtual environment creation
RUN poetry config virtualenvs.create false

# Install dependencies
RUN poetry install --no-root

# Copy the rest of the application code into the container
COPY . .

# Set PYTHONPATH to include the app directory
ENV PYTHONPATH=/app

# Give execute permissions to prestart.sh and convert to Unix line endings
# RUN chmod +x prestart.sh && dos2unix prestart.sh

# Run the prestart script
# RUN poetry run bash ./prestart.sh

# Expose the port that the app runs on
EXPOSE 8000

# Command to start the backend server
CMD ["poetry", "run", "uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000", "--reload"]

