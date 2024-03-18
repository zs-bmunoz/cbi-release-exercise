FROM python:alpine3.19 as builder

# Set tools versions
ENV YQ_VERSION="v4.42.1"

# Update and install required packages
RUN apk update \
 && apk add --no-cache \
    git="2.34.2-r0" \
    unzip="6.0-r9" \
    groff="1.22.4-r1" \
    build-base="0.5-r2" \
    libffi-dev="3.4.2-r1" \
    cmake="3.22.1-r0" \
    jq="1.6-r1" \
    curl="7.80.0-r1" \
    openssh="8.8_p1-r0" \
    gnupg="2.2.31-r0" \
    py3-pip="20.3.4-r1"

# Install python packages
RUN pip install --no-cache-dir \
    deepdiff=="5.7.0" \
    tabulate=="0.8.9" \
    gitpython=="3.1.24"

# Install yq
RUN curl -LO "https://github.com/mikefarah/yq/releases/download/${YQ_VERSION}/yq_linux_amd64" \
 && chmod u+x yq_linux_amd64 \
 && mv yq_linux_amd64 /usr/local/bin/yq