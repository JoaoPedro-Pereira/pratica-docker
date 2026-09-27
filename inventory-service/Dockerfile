# Etapa de Build e instalação de dependências

FROM node:22-alpine AS builder

WORKDIR /app

COPY package*.json ./
RUN npm ci 

# Etapa de construção da imagem de produção (imagem que será rodada)

FROM node:22-alpine AS production

WORKDIR /app

ENV NODE_ENV=production

COPY package*.json ./
RUN npm ci --omit=dev

COPY . .

EXPOSE 3002

CMD ["npm","start"]