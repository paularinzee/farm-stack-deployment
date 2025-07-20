# Use official Python base image
FROM python:3.11-slim

# Set working directory inside the container
WORKDIR /app

# Install system dependencies
RUN apt-get update && apt-get install -y build-essential

# Copy requirements file and install Python dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy your backend source code
COPY . .

# Set environment variable to avoid buffering Python output
ENV PYTHONUNBUFFERED=1

# Expose FastAPI port
EXPOSE 3001

# Start FastAPI using Uvicorn
CMD ["uvicorn", "server:app", "--host", "0.0.0.0", "--port", "3001"]
