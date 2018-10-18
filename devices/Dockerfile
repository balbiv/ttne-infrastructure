# Use an official Ubuntu Xenial as a parent image
FROM ubuntu:16.04

# Install Node.js 8
RUN apt-get update && apt-get install -y \
	build-essential \
	curl \
	apt-transport-https 
	
RUN curl -sL https://deb.nodesource.com/setup_8.x | bash -
RUN apt-get install -y nodejs

# Set the working directory to /app
WORKDIR /app

# Copy the current directory contents into the container
COPY . /app

# Install any needed packages specified in requirements.txt
RUN npm install
RUN npm install dotenv

# Make port 3002 available outside this container
EXPOSE 3002

# Run `npm run serve` when the container launches
CMD ["npm", "start"]
