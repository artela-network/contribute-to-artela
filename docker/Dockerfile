# Builder Image
FROM golang:1.21-bookworm AS builder

ARG GIT_REPOSITORY
ARG IMAGE_TAG

WORKDIR /app

RUN apt-get update && apt-get upgrade -y
RUN git clone --depth 1 --branch $IMAGE_TAG $GIT_REPOSITORY . && make build

### Node Image create
FROM debian:bookworm-slim

ARG BIN
ARG GIT_REPOSITORY
ARG IMAGE_TAG
ARG NODE_TYPE

LABEL image-tag=$IMAGE_TAG
LABEL node-type=$NODE_TYPE

ENV BIN=$BIN
ENV NODE_TYPE=$NODE_TYPE

RUN apt-get update && apt-get upgrade -y \
    && apt-get install -y tzdata ca-certificates curl wget jq expect \
    && apt-get -y purge && apt-get -y clean \
    && apt-get -y autoremove && rm -rf /var/lib/apt/lists/*

COPY --from=builder /app/build/${BIN} /usr/bin/${BIN}
COPY ./run_node.sh .

RUN chmod +x ./run_node.sh

ENTRYPOINT [ "./run_node.sh" ]
