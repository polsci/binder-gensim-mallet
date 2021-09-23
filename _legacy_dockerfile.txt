FROM openjdk:8

RUN apt-get update && \
    apt-get install -y software-properties-common && \
    apt-get install -y python3 python3-pip && \
    apt-get clean;

# install the notebook package - pip3 install --no-cache --upgrade pip && \
RUN pip3 install --no-cache notebook nltk gensim==3.8

ADD http://mallet.cs.umass.edu/dist/mallet-2.0.8.tar.gz /
RUN tar -zxf /mallet-2.0.8.tar.gz
ENV PATH="/mallet-2.0.8/bin:${PATH}"

# create user with a home directory
ARG NB_USER=jovyan
ARG NB_UID=1000
ENV USER ${NB_USER}
ENV NB_UID ${NB_UID}
ENV HOME /home/${NB_USER}

RUN adduser --disabled-password \
    --gecos "Default user" \
    --uid ${NB_UID} \
    ${NB_USER}
WORKDIR ${HOME}
USER ${USER}

# Make sure the contents of our repo are in ${HOME}
COPY ./topic-modeling-with-binder-gensim-mallet.ipynb ${HOME}
USER root
RUN chown -R ${NB_UID} ${HOME}
USER ${NB_USER}
