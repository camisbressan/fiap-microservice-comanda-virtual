# Imagem de Origem
FROM node:13-alpine
# Diretório de trabalho(é onde a aplicação ficará dentro do container).
WORKDIR /client
# Adicionando `/app/node_modules/.bin` para o $PATH
ENV PATH /client/node_modules/.bin:$PATH
# Instalando dependências da aplicação e armazenando em cache.
COPY package.json /client/package.json
RUN npm install npm@latest -g
# start app
CMD ["npm", "start"]
