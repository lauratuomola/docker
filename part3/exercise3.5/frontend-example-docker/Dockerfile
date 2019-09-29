FROM ubuntu:16.04 as build-stage

ENV API_URL=http://localhost:8000

RUN apt-get update && apt-get install -y curl && \
    curl -sL https://deb.nodesource.com/setup_10.x | bash && \
    apt-get install -y nodejs && \
    apt-get purge -y --auto-remove curl && \
    rm -rf /var/lib/apt/lists/*

WORKDIR /app
COPY . .
RUN npm install
RUN npm run build

FROM nginx

COPY --from=build-stage /app/dist /usr/share/nginx/html


