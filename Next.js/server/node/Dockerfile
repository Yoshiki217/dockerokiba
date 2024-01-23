FROM debian
RUN apt-get update && \
    apt-get install -y ca-certificates curl gnupg && \
    mkdir -p /etc/apt/keyrings && \
    curl -fsSL https://deb.nodesource.com/gpgkey/nodesource-repo.gpg.key | gpg --dearmor -o /etc/apt/keyrings/nodesource.gpg && \
    NODE_MAJOR=20 && \
    apt-get update && \
    apt-get install nodejs -y && \
    apt-get install npm -y

RUN groupadd -g 10000 node && \
    useradd -m -u 10000 -g 10000 -s /bin/bash -r node

COPY ./entrypoint.sh /usr/local/bin
RUN chmod 755 /usr/local/bin/entrypoint.sh

USER node

EXPOSE 3000

ENTRYPOINT ["entrypoint.sh"]
CMD ["node"]