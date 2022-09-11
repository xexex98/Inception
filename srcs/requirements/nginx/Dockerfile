FROM alpine:latest

RUN apk update && \
    apk --no-cache add nginx
    
		
RUN	adduser -D -g 'www' www && \
    mkdir /www && \
    chown -R www:www /var/lib/nginx && \
    chown -R www:www /www
		
COPY ./conf/* /etc/nginx/conf.d/

# COPY ./default.conf /etc/nginx/conf.d/

EXPOSE 80

CMD [ "nginx", "-g", "daemon off;" ]