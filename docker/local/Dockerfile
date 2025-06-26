ARG PYTHON_IMAGE=python:3.10-slim
ARG PYTHON_PORT=10000
FROM python:3.10-slim

# Set environment variables
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

# Set the working directory in the container
WORKDIR /app

# Copy the requirements file into the container
COPY requirements.txt .

# Install any needed packages specified in requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Copy the contents of the Django project into the container
COPY .app/ .
COPY .env .env

# Expose the port your app runs on
EXPOSE ${PYTHON_PORT}

# Run your application
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "10000"]
