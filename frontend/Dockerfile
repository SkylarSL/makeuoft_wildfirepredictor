# base image
FROM node:12.2.0

# set working directory
WORKDIR /frontend
RUN npm install
# add `/web/node_modules/.bin` to $PATH
ENV PATH /frontend/node_modules/.bin:$PATH

# install and cache web dependencies
RUN npm config set unsafe-perm true
COPY package.json /frontend/package.json
RUN npm install
RUN npm install @vue/cli@3.7.0 -g

# start web
CMD ["npm", "run", "build"]