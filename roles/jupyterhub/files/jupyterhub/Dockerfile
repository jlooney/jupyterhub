FROM jupyter/jupyterhub

ADD . /jupyterhub

WORKDIR /root
RUN git clone https://github.com/TACC/dockerspawner.git
WORKDIR /root/dockerspawner
RUN pip3 install -r requirements.txt
RUN python3 setup.py install

WORKDIR /root
RUN pip3 install git+git://github.com/TACC/oauthenticator.git

RUN mkdir /srv/oauthenticator
WORKDIR /srv/oauthenticator
ENV OAUTHENTICATOR_DIR /srv/oauthenticator
RUN chmod 700 /srv/oauthenticator
