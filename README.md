Docker file content:
# Use the official Python image
FROM python:3.11.4-slim

# Set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# Set the working directory in the container
WORKDIR /app

# Copy the requirements file into the container at /app
COPY requirements.txt /app/

# Install any dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the application code into the container at /app
COPY . /app/

# Expose the port the app runs on
EXPOSE 5000

# Command to run the application
CMD ["python", "app.py"]

# host='0.0.0.0', port=5000
# sudo apt install unrar
# unrar x /path/to/your/file.rar /path/to/extract

