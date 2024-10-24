FROM node:15 as builder

WORKDIR ./codebase/rdicidr-0.1.0

COPY package*.json ./

RUN npm install

COPY . .

RUN npm run build

FROM node:15

WORKDIR /app

COPY --from=builder ./codebase/rdicidr-0.1.0 /app

RUN npm install --only=production

EXPOSE 3000

ENTRYPOINT ["npm","start"]
