# Use an official Ubuntu Xenial as a parent image
FROM ubuntu:16.04

# Add mqtt repo & update
RUN apt-get update -qq
RUN apt-get install -y software-properties-common
RUN apt-add-repository -y ppa:mosquitto-dev/mosquitto-ppa
RUN apt-get update -qq 
RUN apt-get install -y mosquitto

EXPOSE 1883
EXPOSE 9001
