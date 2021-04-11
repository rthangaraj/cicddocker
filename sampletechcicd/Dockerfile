FROM chuckwired/port-tutorial

# Add path to Env variables
ENV workdir /home/hello-world/

# set the working directory
WORKDIR ${workdir}

COPY app.js ${workdir}

# This is update the systen and install express
RUN sudo apt-get update \
    # Install NPM express
    && npm install -g express

EXPOSE 8080
CMD ["/usr/bin/nodejs", "/home/hello-world/app.js"]
