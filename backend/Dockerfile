# File: GymManager/Dockerfile
# Base image
FROM python:3.12

# Set working directory
WORKDIR /usr/src/app

# Install dependencies
RUN apt-get update && apt-get install -y gcc libpq-dev

# Copy requirements and install
COPY backend/requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy backend code
COPY backend/ .

# Set environment variables
ENV PYTHONUNBUFFERED=1

# Expose port
EXPOSE 8000

# Start server
CMD ["gunicorn", "config.wsgi:application", "--bind", "0.0.0.0:8000"]
