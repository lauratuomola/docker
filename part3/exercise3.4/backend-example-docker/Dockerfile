FROM node:10-alpine

ENV FRONT_URL=http://localhost:5000

RUN adduser -D app 


WORKDIR /app
COPY . .
RUN chown -R app:app /app
USER app

RUN npm install

EXPOSE 8000

CMD ["npm", "start"]

