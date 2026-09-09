# --- STAGE 1: Builder ---
FROM node:24-alpine AS builder
WORKDIR /app

# Activation de pnpm via Corepack
RUN corepack enable && corepack prepare pnpm@10.33.0 --activate

# Installation des dépendances
COPY package.json pnpm-lock.yaml ./
RUN pnpm install --frozen-lockfile

# Copie des sources et compilation
COPY . .
RUN npm run build

# --- STAGE 2: Runtime Non-Root ---
FROM node:24-alpine AS runner
WORKDIR /app

ENV NODE_ENV=production
ENV PORT=3000
ENV HOST=0.0.0.0

# Sécurisation : utilisation d'un utilisateur sans privilèges
USER node

# Copie uniquement de l'output Nitro (build optimisé)
COPY --chown=node:node --from=builder /app/.output ./.output

EXPOSE 3000

CMD ["node", ".output/server/index.mjs"]