FROM python:alpine3.19 as builder

# Set tools versions
ENV YQ_VERSION="v4.42.1"

# Update and install required packages
RUN apk update \
 && apk add --no-cache \
    git="2.44.0-r0" \
    unzip="6.0-r9" \
    groff="1.23.0-r2" \
    build-base="0.5-r2" \
    libffi-dev="3.4.6-r0" \
    cmake="3.28.3-r0" \
    jq="1.7.1-r0" \
    curl="8.6.0-r0" \
    openssh="9.7_p1-r0" \
    gnupg="2.4.4-r0" \
    py3-pip="24.0-r0"

# Install python packages
RUN pip install --no-cache-dir \
    deepdiff=="6.7.1" \
    tabulate=="0.9.0" \
    gitpython=="3.1.42"

# Install yq
RUN curl -LO "https://github.com/mikefarah/yq/releases/download/${YQ_VERSION}/yq_linux_amd64" \
 && chmod u+x yq_linux_amd64 \
 && mv yq_linux_amd64 /usr/local/bin/yq