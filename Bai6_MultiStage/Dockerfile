FROM node:18 AS builder
WORKDIR /app
COPY package.json .
COPY app.js .
RUN npm install
RUN npm run build

FROM node:18-alpine
WORKDIR /app
COPY --from=builder /app /app
EXPOSE 3000
CMD ["npm", "start"]