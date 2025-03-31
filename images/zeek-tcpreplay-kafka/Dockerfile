FROM zeek/zeek:6.1.0

# Install dependencies
RUN apt-get update && \
    apt-get install -y \
      bison \
      clang \
      cmake \
      flex \
      g++ \
      gcc \
      git \
      iproute2 \
      libssl-dev \
      librdkafka-dev \
      libpcap-dev \
      make \
      net-tools \
      softflowd \
      swig \
      tcpreplay \
      zlib1g-dev \
      python3 \
      python3-pip \
      python3-venv && \
    rm -rf /var/lib/apt/lists/*

# Build and install Kafka plugin from SeisoLLC repo
RUN git clone --depth 1 https://github.com/SeisoLLC/zeek-kafka.git /tmp/zeek-kafka && \
    cd /tmp/zeek-kafka && \
    ./configure && \
    make && \
    make install && \
    rm -rf /tmp/zeek-kafka
