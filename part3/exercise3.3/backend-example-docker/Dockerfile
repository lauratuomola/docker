FROM ubuntu:16.04 

ENV FRONT_URL=http://localhost:5000

RUN apt-get update && apt-get install -y curl && \
    curl -sL https://deb.nodesource.com/setup_10.x | bash && \
    apt-get install -y nodejs && \
    apt-get purge -y --auto-remove curl && \
    rm -rf /var/lib/apt/lists/* && \
    useradd -m app 


WORKDIR /app
COPY . .
RUN chown -R app:app /app
USER app

RUN npm install

EXPOSE 8000

CMD ["npm", "start"]

