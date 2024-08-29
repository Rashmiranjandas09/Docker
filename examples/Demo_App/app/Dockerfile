# Use the official Python image from the Docker Hub
FROM python:3.9-slim

# Set environment variables to prevent Python from writing .pyc files and to buffer stdout and stderr
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

# Set the working directory inside the Docker image
WORKDIR /app

# Copy the requirements file to the working directory
COPY requirements.txt /app/

# Install dependencies
RUN pip install --upgrade pip && pip install -r requirements.txt

# Copy the Django project files into the Docker image
COPY . /app/

# Expose the port on which Django will run
EXPOSE 8000

# Run Django's development server
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
