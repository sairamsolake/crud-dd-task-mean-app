# Backend Dockerfile - Node/Express
FROM node:18-alpine AS builder
WORKDIR /app

# copy package files and install dependencies
COPY package*.json ./
RUN npm ci

# copy source
COPY . .

# If you have build steps (tsc etc) add them here:
# RUN npm run build

# runtime image
FROM node:18-alpine
WORKDIR /app
ENV NODE_ENV=production
COPY --from=builder /app ./

# ensure non-root user
RUN chown -R node:node /app
USER node

EXPOSE 3000
# use the environment variable PORT if set by docker-compose; fallback to 3000
CMD ["sh", "-c", "node ${ENTRYPOINT:-server.js}"]

