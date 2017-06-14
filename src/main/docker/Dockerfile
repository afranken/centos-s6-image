FROM centos:7

# s6 overlay
ADD https://github.com/just-containers/s6-overlay/releases/download/v1.19.1.1/s6-overlay-amd64.tar.gz /tmp/s6-overlay-amd64.tar.gz
# this overly complicated tar call is needed since the s6-overlay-tar would otherwise overwrite the "/bin" and "/sbin" links
RUN tar xzfv /tmp/s6-overlay-amd64.tar.gz -C / --exclude="./bin" \
    && tar xzfv /tmp/s6-overlay-amd64.tar.gz -C /usr ./bin \
    && rm /tmp/s6-overlay-amd64.tar.gz

#DO NOT OVERWRITE
#this entrypoint will start s6 and with it all run scripts added by overlays.
ENTRYPOINT [ "/init" ]
