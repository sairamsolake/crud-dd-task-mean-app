FROM node:20-alpine

WORKDIR /app

# Copy package files
COPY package*.json ./

# Use npm install instead of npm ci (because lock file is mismatched)
RUN npm install --legacy-peer-deps

# Copy source code
COPY . .

EXPOSE 5000

CMD ["npm", "start"]
