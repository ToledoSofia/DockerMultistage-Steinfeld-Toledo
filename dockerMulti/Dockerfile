FROM node:latest AS builder

COPY estilos.css /app/estilos.css
COPY script.js /app/script.js

RUN npm install npm install uglify-js -g
RUN npm install -g uglifycss

RUN uglifycss /app/estilos.css > /app/estilos.min.css
RUN uglifyjs /app/script.js -o /app/script.min.js

FROM nginx:latest

COPY --from=builder /app/estilos.min.css /usr/share/nginx/html/estilos.css
COPY --from=builder /app/script.min.js /usr/share/nginx/html/script.js
COPY index.html /usr/share/nginx/html/index.html
COPY default.conf /etc/nginx/conf.d/default.conf
EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
