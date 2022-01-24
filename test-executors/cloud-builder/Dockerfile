# This dockerfile produces a Linux image that has the minimum capabilities
# required to build and test a 

# Start with a minimal Ubuntu base image. This is basically 30MB but has almost
# nothing in it.
FROM ubuntu:20.04

# Install the base packages.
RUN apt-get update
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y \
    tzdata \
    curl \
    unzip \
    git \
    # The following packages are required by Bazel.
    # Note: Python is only required as a workaround for https://github.com/bazelbuild/bazel/issues/11554.
    python-is-python3 \
    patch \
    build-essential \
    imagemagick \
    && apt-get clean

# Install NVM, which we can use later to install Node.
# Note that after installed, nvm is just a function in the user's environment, so you
# have to source it first via "source ~/.nvm/nvm.sh" before you can use it (or npm, etc...).
RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
