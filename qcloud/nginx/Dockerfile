FROM nginx:latest

ADD . /var/www/
COPY ./qcloud/nginx/nginx.conf /etc/nginx/nginx.conf
COPY ./qcloud/nginx/default.conf /etc/nginx/conf.d/default.conf

CMD ["nginx","-g","'daemon off;'"]

EXPOSE 80