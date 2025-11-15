# base defines a base stage that uses the official python runtime base image
FROM python:3.11-slim

#Create the directory /data
RUN mkdir -p /data

#Add volume /data
VOLUME ["/data"]

# Install Flask engine for our API
RUN apt update -y && apt install -y python3 python3-pip python3-dev build-essential libsasl2-dev libldap2-dev libssl-dev -y

# Add our source code
COPY student_age.py /student_age.py

# Install our requirements.txt
COPY requirements.txt /requirements.txt
RUN pip3 install -r /requirements.txt


# Make port 5000 available for links and/or publish
EXPOSE 5000

# Define our command to be run when launching the container
CMD [ "python3", "./student_age.py" ]
