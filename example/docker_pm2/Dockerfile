FROM node:lts-alpine

WORKDIR /app

RUN npm update -g npm@latest
RUN npm install --global pm2
RUN npm install -g next@latest

# Copy "package.json" and "package-lock.json" before other files
# Utilise Docker cache to save re-installing dependencies if unchanged
COPY ./package*.json ./

RUN npm install --silent --legacy-peer-deps

COPY .env .env
COPY ./ ./

ENV NODE_ENV=production
RUN npm run build

EXPOSE 3000

USER node

CMD [ "pm2-runtime", "start", "npm", "--", "start" ]