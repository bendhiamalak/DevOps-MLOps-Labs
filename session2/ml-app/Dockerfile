# Use official Python runtime as base image
FROM python:3.10-slim

# Set working directory
WORKDIR /app

# Copy requirements and install dependencies
COPY requirements.txt .
RUN pip install --upgrade pip && \
    pip install -r requirements.txt && \
    pip install pytest flake8

# Copy all project files
COPY . .

# Create directory for storing trained models
RUN mkdir -p models

# Expose port if using Flask (optional)
# EXPOSE 5000

# Run linter (optional, can comment if not needed)
# RUN flake8 src/ tests/

# Run tests (optional, can comment if not needed)
# RUN pytest --maxfail=1 --disable-warnings -q

# Default command to train the model
CMD ["python", "src/train.py"]
