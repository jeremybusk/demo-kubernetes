FROM alpine
RUN apk add curl
# RUN curl -LO https://github.com/coredns/coredns/releases/download/v1.8.1/coredns_1.8.1_linux_amd64.tgz -o file.tgz
ADD https://github.com/coredns/coredns/releases/download/v1.8.1/coredns_1.8.1_linux_amd64.tgz
RUN tar xf coredns_1.8.1_linux_amd64.tgz
RUN curl -LO https://raw.githubusercontent.com/jeremybusk/share/master/Corefile
CMD ./coredns

# Options
# WORKDIR /app
# COPY and ADD(url) are options too
