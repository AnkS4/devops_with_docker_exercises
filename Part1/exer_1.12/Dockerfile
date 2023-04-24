FROM node:16
WORKDIR /usr/src/app
EXPOSE 5000
RUN git clone https://github.com/docker-hy/material-applications
RUN mv material-applications/example-frontend/* .
RUN npm install
RUN npm run build
RUN npm install -g serve
# RUN serve -s -l 5000 build
CMD ["serve", "-s", "-l", "5000", "build"]
