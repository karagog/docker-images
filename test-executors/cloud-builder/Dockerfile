# This dockerfile produces a Linux image that has the minimum capabilities
# required to build and test a 

# Start with a minimal Ubuntu base image. This is basically 30MB but has almsot
# nothing in it.
FROM ubuntu:20.04

# Install the base packages.
RUN apt-get update && apt-get install -y \
    curl \
    git \
    # The following packages are required by Bazel.
    # Note: Python is only required as a workaround for https://github.com/bazelbuild/bazel/issues/11554.
    python-is-python3 \
    patch \
    build-essential

# Install Docker. Note that there doesn't seem to be a working package in Ubuntu's package repository
# so we install from a script.
RUN curl -sSL https://get.docker.com/ | sh