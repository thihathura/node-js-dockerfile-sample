Install Node-js app on Docker

1st Download the Source Code

2nd Enter the folder -> named app

3th Dockerfile
FROM node:12-alpine
RUN apk add --no-cache python2 g++ make
WORKDIR /app
COPY . .
RUN yarn install --production
CMD ["node", "src/index.js"]
EXPOSE 3000

4th Build the DockerImage
  docker build -t my-demo-node-js .

5th Run as the Container  (Note - Expose Port is 3000)
  docker run -d -p 3000:3000 my-demo-node-js