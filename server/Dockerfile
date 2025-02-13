FROM ubuntu:22.04

# Устанавливаем нужные библиотеки
RUN apt-get update && apt-get install -y \
    libstdc++6 libc6 libpq-dev odbcinst1debian2 unixodbc \
    && rm -rf /var/lib/apt/lists/*

RUN apt-get update && apt-get install -y software-properties-common \
    && add-apt-repository -y ppa:ubuntu-toolchain-r/test \
    && apt-get update && apt-get install -y libstdc++6

# Копируем бинарник
COPY /artifacts/graphql-engine-linux /bin/graphql-engine-linux
RUN chmod +x /bin/graphql-engine-linux

CMD ["/bin/graphql-engine-linux", "serve"]
