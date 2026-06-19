FROM ubuntu:latest
#base image is added

LABEL dev='aqsa'
#giving tags to the docker

RUN apt-get update && \
    apt-get install apache2 unzip -y && \
    rm -rf /var/www/html/index.html
    # we installed web server package, unzip package and updated system

    ADD https://templatemo.com/download/templatemo_625_folio_slideshow  /var/www/html/templatemo_625_folio_slideshow.zip
    # add will download the static page from internet and move it in /var/www/html location

    WORKDIR /var/www/html
    # switching directories to /var/www/html

    RUN unzip templatemo_625_folio_slideshow.zip && \
    mv  templatemo_625_folio_slideshow/* /var/www/html/
    # unzip the dir and moved static code into the /var/www/html

    EXPOSE 80
    #the conatiner will be having 80 port open

    CMD ["apache2ctl", "-D", "FOREGROUND"]
    #cmd is used to start the single running process on docker

