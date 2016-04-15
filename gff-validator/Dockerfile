#------------------------------------------------------------
# Dockerfile to build various tools for validating GFF v3
#------------------------------------------------------------
FROM debian:jessie

ENV GT_VERSION 1.5.8

MAINTAINER Josh Goodman <jogoodma@indiana.edu>

#Install dependencies.
#List::MoreUtils is required by the GAL GFF v3 validator.
RUN apt-get update && apt-get install -y \
        build-essential \
        gcc-multilib \
        liblist-moreutils-perl \ 
        wget \
        vim \
        less \
        subversion

# Download genometools sources 
RUN wget http://genometools.org/pub/genometools-$GT_VERSION.tar.gz && \
    tar zxf genometools-$GT_VERSION.tar.gz 

# Compile and install genometools
WORKDIR /genometools-$GT_VERSION/

RUN make 64bit=yes cairo=no install

WORKDIR /

#Fetch GAL from their svn server.
RUN svn co svn://topaz.genetics.utah.edu/GAL/trunk GAL

