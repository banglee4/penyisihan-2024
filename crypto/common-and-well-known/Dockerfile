FROM ubuntu:22.04
RUN apt-get update && \
    apt-get -y install python3 socat python3-pip && \
    rm -rf /var/lib/apt/lists/*

RUN pip3 install pycryptodome

WORKDIR /home/nobody
COPY /crypto/broken-chall/src .

USER nobody
EXPOSE 9999
CMD socat TCP-LISTEN:9999,reuseaddr,fork EXEC:"python3 -u chall.py"
