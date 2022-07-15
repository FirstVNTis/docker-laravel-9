FROM nginx:1.20.1

ENV TERM xterm

COPY ./docker/nginx/nginx.conf /etc/nginx/nginx.conf
ADD ./docker/nginx/conf.d/app.conf /etc/nginx/conf.d/app.conf
COPY ./docker/nginx/conf.d/upstream.conf /etc/nginx/conf.d/upstream.conf

RUN mkdir -p /var/www

# Create user for laravel application
RUN usermod -G www-data -g www-data -s /bin/sh -u 1000  www-data

# Set permissions
RUN chown www-data:www-data /var/www

CMD ["nginx"]

EXPOSE 80 443
