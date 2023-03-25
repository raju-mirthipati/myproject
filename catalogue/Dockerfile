FROM node:14

ENV INSTANA_AUTO_PROFILE true

WORKDIR /opt/server

# create the 'catalogue' group
RUN addgroup catalogue

# create the 'catalogue1' user and add it to the 'catalogue' group
RUN useradd -m -s /bin/bash -g catalogue catalogue1 && usermod -aG catalogue catalogue1

# change the ownership of the '/opt/server' directory to 'catalogue:catalogue'
RUN chown catalogue1:catalogue /opt/server

USER catalogue1

EXPOSE 8080

COPY package.json /opt/server/

RUN npm install

COPY server.js /opt/server/

CMD ["node", "server.js"]
