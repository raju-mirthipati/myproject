FROM node:14

ENV INSTANA_AUTO_PROFILE true

WORKDIR /opt/server

RUN addgroup catalogue && adduser catalogue1 && usermod -aG catalogue1 catalogue

RUN chown catalogue:catalogue /opt/server

USER catalogue1

EXPOSE 8080

COPY package.json /opt/server/

RUN npm install

COPY server.js /opt/server/

CMD ["node", "server.js"]

