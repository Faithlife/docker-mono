FROM ubuntu:xenial

RUN apt-get update \
  && apt-get install -y \
    apt-transport-https \
    curl \
  && rm -rf /var/lib/apt/lists/*

RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF \
  && echo "deb http://download.mono-project.com/repo/debian xenial/snapshots/5.8 main" > /etc/apt/sources.list.d/mono-xamarin.list

RUN curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > /etc/apt/trusted.gpg.d/microsoft.gpg
RUN echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-xenial-prod xenial main" > /etc/apt/sources.list.d/dotnetdev.list

ARG DOTNET_SDK_VERSION=2.1.4

RUN apt-get update \
  && apt-get install -y \
    dotnet-sdk-${DOTNET_SDK_VERSION} \
    mono-devel \
    nuget \
    tzdata \
  && rm -rf /var/lib/apt/lists/*
