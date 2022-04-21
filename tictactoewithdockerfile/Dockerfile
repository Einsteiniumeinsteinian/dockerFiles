FROM	alpine:latest as builder

RUN	apk add --update git && \
	git clone https://github.com/Einsteiniumeinsteinian/Brainy-Tic-Tac-Toe.git


FROM	nginx:latest

#RUN	git clone https://github.com/Einsteiniumeinsteinian/Brainy-Tic-Tac-Toe.git /usr/share/nginx/html/

WORKDIR /usr/share/nginx/html/

COPY	--from=builder /Brainy-Tic-Tac-Toe .

EXPOSE	8001/tcp

CMD	["nginx", "-g", "daemon off;"]
