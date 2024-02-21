FROM python:alpine3.8 as builder

RUN apk update \
 && apk add --no-cache git unzip groff build-base libffi-dev cmake

# Install required packages
RUN apk update \
 && apk add --no-cache jq curl git openssh gnupg unzip py3-pip

# Install python packages
RUN pip install deepdiff tabulate gitpython