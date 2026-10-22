FROM node:18-alpine AS dev

WORKDIR /app

COPY package*.json ./
RUN npm ci --only=production

# Install nodemon globally for local dev override
RUN npm install -g nodemon

COPY . .

RUN adduser -D appuser
RUN chown -R appuser:appuser /app

USER appuser

EXPOSE 80

CMD ["node", "server.js"]