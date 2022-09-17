FROM alpine:3.15

RUN apk update && apk upgrade

RUN apk --no-cache add nginx

RUN mkdir /www 

RUN	mkdir -p /run/nginx

RUN chmod 775 /run/nginx/

COPY ./conf/* /etc/nginx/conf.d/

EXPOSE 80

CMD [ "nginx", "-g", "daemon off;" ]