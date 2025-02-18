FROM mcr.microsoft.com/devcontainers/base:ubuntu

# Instalar dependências básicas
RUN apt-get update && apt-get install -y curl git unzip openjdk-11-jdk

# Instalar Node.js e Expo CLI
RUN curl -fsSL https://deb.nodesource.com/setup_18.x | bash - && \
    apt-get install -y nodejs && \
    npm install -g expo-cli

# Instalar Android SDK
RUN mkdir -p /opt/android-sdk && \
    curl -o android-sdk.zip https://dl.google.com/android/repository/commandlinetools-linux-8512546_latest.zip && \
    unzip android-sdk.zip -d /opt/android-sdk && \
    rm android-sdk.zip

ENV ANDROID_HOME="/opt/android-sdk"
ENV PATH="$ANDROID_HOME/cmdline-tools/bin:$ANDROID_HOME/platform-tools:$PATH"

CMD ["bash"]
