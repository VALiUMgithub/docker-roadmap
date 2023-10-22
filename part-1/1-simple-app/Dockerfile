# Stage 1: Build the application
FROM node:14 AS builder
WORKDIR /usr/src/app
COPY package.json package-lock.json ./
RUN npm install
COPY index.js index.html ./

# Stage 2: Create the production image
FROM node:14-alpine
WORKDIR /usr/src/app
COPY --from=builder /usr/src/app ./
EXPOSE 3000
CMD ["node", "index.js"]
