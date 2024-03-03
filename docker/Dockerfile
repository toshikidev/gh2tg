FROM alpine:3.17

ARG TARGETOS
ARG TARGETARCH

LABEL maintainer="Anda Toshiki <hello@toshiki.dev>" \
  org.label-schema.name="SSH Plugin" \
  org.label-schema.vendor="Anda Toshiki" \
  org.label-schema.schema-version="1.0"

LABEL org.opencontainers.image.source=https://github.com/toshikidev/gh2tg
LABEL org.opencontainers.image.description="GitHub webhook event trigger to forward a message to a Telegram bot"
LABEL org.opencontainers.image.licenses=MIT

RUN apk add --no-cache ca-certificates=20230506-r0 && \
  rm -rf /var/cache/apk/*

COPY release/${TARGETOS}/${TARGETARCH}/gh2tg /bin/

ENTRYPOINT ["/bin/gh2tg"]
