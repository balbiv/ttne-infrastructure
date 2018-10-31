# Use an official Ubuntu Xenial as a parent image
FROM ubuntu:16.04

# Install Node.js 8 and npm 5
RUN apt-get update -qq
RUN apt-get install -y build-essential
RUN apt-get install -y curl
RUN apt-get install -y apt-transport-https
RUN curl -sL https://deb.nodesource.com/setup_8.x | bash -
RUN apt-get update -qq
RUN apt-get install -y nodejs

# Set the working directory to /app
WORKDIR /app

# Copy the current directory contents into the container
COPY . /app

# Install any needed packages specified in requirements.txt
RUN npm install
RUN npm run build
RUN cp -a /app/dist/. /var/www/html

# Make port 8080 available outside this container
EXPOSE 8080

# Start Apache2
CMD service apache2 start
