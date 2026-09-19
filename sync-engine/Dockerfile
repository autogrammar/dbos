FROM node:20-slim@sha256:c610fcdfb1d5b4740dd70c284ed3cb16bb857e0f7166196e36a5501df7a3aa32

RUN apt-get update && apt-get install -y fontconfig fonts-dejavu-core && rm -rf /var/lib/apt/lists/*

WORKDIR /app
COPY package.json ./
RUN npm install --omit=dev

COPY src ./src

CMD ["node", "src/index.js"]
