FROM node:20

WORKDIR /app

COPY package*.json ./

RUN npm ci

COPY . .

# 👇 ADD THIS LINE (IMPORTANT FIX)
ENV NODE_OPTIONS=--openssl-legacy-provider

ENV PORT=5002

EXPOSE 5002

CMD ["npm", "start"]