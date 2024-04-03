FROM ubuntu:22.10

RUN apt-get clean
RUN rm -rf /var/lib/apt/lists/*
RUN apt-get install curl -y
RUN curl --proto '=https' --tlsv1.2 -sSf https://raw.githubusercontent.com/aws-cloudformation/cloudformation-guard/main/install-guard.sh | sh
RUN mkdir -p '/opt/bin'
RUN cp --dereference "/root/.guard/bin/cfn-guard" "/opt/bin/"
ENV PATH "${PATH}:/opt/bin"

COPY ./output/ /
