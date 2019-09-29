FROM node:10-alpine

ENV API_URL=http://localhost:8000

RUN adduser -D app 

WORKDIR /app
COPY . .
RUN chown -R app:app /app
USER app
RUN npm install

EXPOSE 5000

CMD ["npm", "start"]

