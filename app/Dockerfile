FROM node:alpine

# Create app directory
WORKDIR /usr/src/app

# Install app dependencies
# A wildcard is used to ensure both package.json AND package-lock.json are copied
# where available (npm@5+)
COPY package*.json ./

RUN npm install
# If you are building your code for production
# RUN npm ci --only=production

# Bundle app source
COPY . .
# package.jsonをコピー後にnpm installするという作業をビルドの度に毎回やりたくない。
# そのため、上記を終わらせてから COPY. .をやる。
# そうすればコードを変えた部分だけビルドが実行される。

EXPOSE 3000
CMD [ "node", "index.js" ]
