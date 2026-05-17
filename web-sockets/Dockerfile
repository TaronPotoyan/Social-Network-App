FROM node:22-alpine

WORKDIR /app

# Enable Corepack (pnpm)
RUN corepack enable && corepack prepare pnpm@latest --activate

# Copy package files
COPY package.json pnpm-lock.yaml pnpm-workspace.yaml ./

# Install dependencies
RUN pnpm install --frozen-lockfile --ignore-scripts

# Copy source code
COPY . .

EXPOSE 3000

# Development command (hot reload)
CMD ["pnpm", "start:dev"]