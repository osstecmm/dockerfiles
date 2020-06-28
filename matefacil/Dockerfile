# Using Clear Linux
FROM clearlinux:latest

# Who is working on the project?
LABEL maintainer="Luis Manuel Chávez Velasco, Jesús Castro <x51v4n@gmail.com>"

# This keeps Python from buffering stdin/stdout 
ENV PYTHONUNBUFFERED 1

# Copy project repository
COPY program /home/program

# Install the basics required for MateFacil
RUN swupd bundle-add python3-basic
RUN swupd bundle-add java-basic
RUN swupd bundle-add c-basic

# Requiriments needed for Python
COPY requirements.txt /
RUN pip install -r requirements.txt

# Define the working directory 
WORKDIR /home/program/

