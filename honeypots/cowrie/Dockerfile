FROM ubuntu:22.04
RUN apt-get update
RUN apt-get install -y git libssl-dev libffi-dev build-essential libpython3-dev python3-minimal python3-pip
RUN git clone https://github.com/cowrie/cowrie /opt/cowrie
WORKDIR /opt/cowrie
RUN pip3 install -r requirements.txt
RUN cp etc/cowrie.cfg.dist etc/cowrie.cfg
ENTRYPOINT ["bin/cowrie","start",";","tail -f var/log/cowrie/cowrie.log"]