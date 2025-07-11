FROM nginx
LABEL "Prokect"="Vprofile"
LABEL "Author"="Mohannad"
# remove the default configuration
RUN rm -rf /etc/nginx/conf.d/default.conf
# copy our custom configuration file to the location specified in the nginx docs.
COPY nginvporapp.conf /etc/nginx/conf.d/vproapp.conf