# base defines a base stage that uses the official python runtime base image
FROM python:3.11-slim AS base

#Create the directory /data
RUN mkdir -p /data

#Add volume /data
VOLUME ["/data"]

# Install Flask engine for our API
RUN apt-get update && \
    pt install python-dev python3-dev libsasl2-dev python-dev libldap2-dev libssl-dev -y
    rm -rf /var/lib/apt/lists/*

# Add our source code
COPY student_age.py /student_age.py

# Install our requirements.txt
COPY requirements.txt /requirements.txt
pip3 install -r /requirements.txt


# Make port 5000 available for links and/or publish
EXPOSE 5000

# Define our command to be run when launching the container
CMD [ "python3", "./student_age.py" ]
