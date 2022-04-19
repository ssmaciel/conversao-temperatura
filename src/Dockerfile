FROM node:16 as builder

WORKDIR /app

COPY package.json .

RUN npm i

COPY . .

FROM node:16.14-alpine3.15 as final

WORKDIR /app

COPY --from=builder /app /app

EXPOSE 8080

CMD ["node", "server.js"]
