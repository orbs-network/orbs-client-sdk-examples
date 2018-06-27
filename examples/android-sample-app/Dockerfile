FROM debian:stretch

ADD ./bootstrap-sdk.sh /opt/android-sdk/

WORKDIR /opt/android-sdk

RUN ./bootstrap-sdk.sh

ADD . /opt/android-sdk

RUN ./build.sh
