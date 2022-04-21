FROM	node:latest

RUN	git clone https://github.com/Einsteiniumeinsteinian/Todo-App.git

WORKDIR	Todo-App

RUN	npm install && npm audit fix

EXPOSE 3000/tcp

CMD	["node","app.js"]
