FROM node:lts-alpine
WORKDIR /app

COPY .env .env
COPY . .
RUN npm update -g npm@latest
RUN npm install -g next@latest
RUN npm install --silent --legacy-peer-deps

ENV NODE_ENV=production
RUN npm run build 
USER node

EXPOSE 3000

CMD ["npm", "start"]