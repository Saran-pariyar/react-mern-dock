# We'll get node image, use Alpine version as it's lightweight. 
FROM node:20-alpine

# we'll set working directory to /app (this is the directory where commands will run)
# /app is standard convention
WORKDIR /app

# this will copy everything from current dir to docker image
# first . is current dir on our machine & 2nd is path to current dir within the container (/app)
COPY . .

# specify the command to run the app
CMD node hello.js

# now we'll run -> docker build -t hello-docker .
# -t hello-docker means set this image name/tag as hello-docker. Also the . at least means do at current location

#the image has been created. 
# docker run hello-docker -> will output Hello Docker

# go to docker, click respective container, click on files, you'll see /app where all our codes are

# docker run -it hello-docker sh -> we can interact, it will put us to /app in the terminal, there we can do node hello.js to run that js file
