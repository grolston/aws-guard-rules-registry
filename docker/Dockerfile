FROM ubuntu:24.04
RUN apt update && apt -y install curl
RUN apt-get clean
RUN rm -rf /var/lib/apt/lists/*
RUN curl --proto '=https' --tlsv1.2 -sSf https://raw.githubusercontent.com/aws-cloudformation/cloudformation-guard/main/install-guard.sh | sh
RUN mkdir -p '/opt/bin'
RUN cp --dereference "/root/.guard/bin/cfn-guard" "/opt/bin/"
ENV PATH "${PATH}:/opt/bin"

COPY ./output/ /
