FROM node:15

# Setar dir inicial
WORKDIR /usr/src/app

RUN apt-get update && apt-get install -y wget

ENV DOCKERIZE_VERSION v0.6.1
RUN wget https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && tar -C /usr/local/bin -xzvf dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && rm dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz

RUN echo
RUN echo '--- Listagem dos arquivos ---'
RUN ls -la


# Copiar conteúdos da pasta corrente para o workdir inicial do container (dir corrente do container também)
COPY . .

EXPOSE 3000

CMD ["node", "index.js"]