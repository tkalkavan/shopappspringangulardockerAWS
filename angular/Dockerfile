# Create image based on the official Node 6 image from dockerhub
  FROM node:12.16.1-alpine As builder

  # Create a directory where our app will be placed
  RUN mkdir -p /ui.angular

  # Change directory so that our commands run inside this new directory
  WORKDIR /ui.angular

  # Copy dependency definitions
  COPY package.json /ui.angular

  # Install dependencies

  RUN npm install -g @angular/cli @angular-devkit/build-angular && npm install

  # Get all the code needed to run the app
  COPY . /ui.angular


  # Expose the port the app runs in, port 4200
  EXPOSE 4200

  # Serve the app, for localhost
  CMD ng serve --host 0.0.0.0
