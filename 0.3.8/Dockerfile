FROM debian:jessie

MAINTAINER Pyrax <piranhadev@gmail.com> / Mandrakke <pedro.papadopolis@gmail.com>

# SA-MP server executable is a x86 application only
RUN dpkg --add-architecture i386

# Install packages
RUN apt-get update && apt-get install -y \
 lib32stdc++6 \
 wget \
 psmisc

COPY samp.sh /usr/local/bin/samp
COPY docker-entrypoint.sh /entrypoint.sh

RUN chmod +x /usr/local/bin/samp \
 && chmod +x /entrypoint.sh

ENTRYPOINT ["/entrypoint.sh"]

CMD ["samp", "start"]

EXPOSE 7777/udp
EXPOSE 7778/udp