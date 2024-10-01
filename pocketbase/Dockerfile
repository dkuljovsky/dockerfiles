FROM alpine:latest

ARG version=0.22.21

WORKDIR /app

COPY ./pb_hooks ./pb_hooks

RUN apk add --no-cache unzip

RUN wget https://github.com/pocketbase/pocketbase/releases/download/v${version}/pocketbase_${version}_linux_arm64.zip \
  && unzip pocketbase_${version}_linux_arm64.zip \
  && rm pocketbase_${version}_linux_arm64.zip

RUN chmod +x pocketbase

EXPOSE 8090

CMD ["./pocketbase", "serve", "--http", "0.0.0.0:8090"]