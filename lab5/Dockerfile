FROM scratch
ADD alpine-minirootfs-3.21.3-aarch64.tar /

FROM nginx:alpine
WORKDIR /usr/share/nginx/html

ARG VERSION=1.0

COPY index.html .
COPY hostname.txt .

RUN echo "$VERSION" > version.txt

RUN ip addr show eth0 | grep "inet " | awk '{print $2}' | cut -d/ -f1 > server-ip.txt || echo "Nieznane IP" > server-ip.txt

COPY nginx.conf /etc/nginx/nginx.conf

EXPOSE 80

HEALTHCHECK --interval=30s --timeout=5s --start-period=10s --retries=3 \
    CMD curl -f http://localhost || exit 1
