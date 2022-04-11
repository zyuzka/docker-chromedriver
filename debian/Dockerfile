FROM debian:bullseye-slim

ARG CHROMIUM_VERSION=100.0.4896.60-r0

RUN useradd -u 1000 -m -U webdriver

WORKDIR /home/webdriver

RUN export DEBIAN_FRONTEND=noninteractive \
  && apt-get update \
  && apt-get dist-upgrade -y \
  && apt-get install --no-install-recommends --no-install-suggests -y \
    ca-certificates \
    curl \
    chromium-driver \
    chromium

RUN ln -s /usr/lib/chromium/chromium /usr/local/bin/chrome

USER webdriver

ENTRYPOINT ["chromedriver"]

CMD ["--port=4444", "--whitelisted-ips="]

EXPOSE 4444
