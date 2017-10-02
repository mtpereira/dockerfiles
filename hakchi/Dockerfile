FROM ubuntu:16.04

RUN apt-get update \
    && apt-get install --yes \
      libusb-1.0-0-dev \
      libqt4-dev \
      upx-ucl \
      cpio \
      lzop \
      wget \
      build-essential \
      git \
      pkg-config

WORKDIR /hakchi
COPY . .
RUN make

ENTRYPOINT ["./entrypoint.sh"]

