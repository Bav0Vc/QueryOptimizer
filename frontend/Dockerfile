FROM node:20-alpine

WORKDIR /app

# Exposeer de poort van Vite
EXPOSE 5173

# Start de Vite dev server met host-flag zodat Docker hem kan mappen
CMD npm install && npm run dev -- --host