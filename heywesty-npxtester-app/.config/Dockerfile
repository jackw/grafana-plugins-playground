ARG grafana_version=latest
ARG grafana_image=grafana

FROM grafana/${grafana_image}:${grafana_version}

# Set development mode so plugins can be loaded without the need to sign
ENV GF_DEFAULT_APP_MODE "development"

