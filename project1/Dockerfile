FROM ubuntu:latest

# Update the package list and install Python3, pip, and venv
RUN apt-get update && \
    apt-get install -y python3 python3-pip python3-venv && \
    apt-get clean

# Set up a virtual environment
WORKDIR /app
RUN python3 -m venv venv
ENV PATH="/app/venv/bin:$PATH"

# Install requirements in the virtual environment
COPY requirements.txt /app
COPY devops /app
RUN pip install -r requirements.txt

# Run your script
CMD ["python3", "manage.py", "runserver", "0.0.0.0:8000"]


