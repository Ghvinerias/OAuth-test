FROM node:20-slim

ENV PNPM_HOME="/pnpm"
ENV PATH="$PNPM_HOME:$PATH"
RUN corepack enable
WORKDIR /app

# Install dependencies based on the preferred package manager
COPY ./* ./
EXPOSE 5173
RUN pnpm install
CMD pnpm run dev --host 0.0.0.0