# This dockerfile produces a Linux image that has the minimum capabilities
# required to build and test a 

# Start with a minimal Ubuntu base image. This is basically 30MB but has almsot
# nothing in it.
FROM ubuntu:20.04

# Install the base packages.
RUN apt-get update && \
  apt-get install -y \
    git \
    # We need the root CA certificates for example when downloading Go packages,
    # otherwise we don't know whose certificates to trust.
    ca-certificates \
    # These packages are required by Bazel.
    # Note: Python is only required as a workaround for https://github.com/bazelbuild/bazel/issues/11554.
    python-is-python3 \
    patch \
    build-essential