FROM arm64v8/ubuntu:22.04

RUN apt-get update -y 

RUN apt install -y build-essential libcairo2-dev libjpeg-turbo8-dev tar wget\
    libpng-dev libtool-bin libossp-uuid-dev libvncserver-dev\
    freerdp2-dev libssh2-1-dev libtelnet-dev libwebsockets-dev\
    libpulse-dev libvorbis-dev libwebp-dev libssl-dev\
    libpango1.0-dev libswscale-dev libavcodec-dev libavutil-dev\
    libavformat-dev libguac-client-rdp0 libguac-client-ssh0

RUN wget https://dlcdn.apache.org/guacamole/1.5.5/source/guacamole-server-1.5.5.tar.gz &&\
    tar -xvf guacamole-server-1.5.5.tar.gz && rm -rf guacamole-server-1.5.5.tar.gz &&\
    cd guacamole-server-1.5.5 &&\
    ./configure --with-init-dir=/etc/init.d &&\
    make &&\
    make install &&\
    ldconfig &&\
    cd .. && rm -rf guacamole-server-1.5.5

CMD ["/usr/local/sbin/guacd", "-f", "-b", "127.0.0.1", "-l", "4822", "-L", "debug"]