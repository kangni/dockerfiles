FROM ubuntu:latest

WORKDIR /workspace

RUN sed -i 's/archive.ubuntu.com/mirrors.ustc.edu.cn/g' /etc/apt/sources.list \
&& apt update \
&& apt install apt-transport-https curl gnupg wget g++ unzip zip \
&& curl -fsSL https://bazel.build/bazel-release.pub.gpg | gpg --dearmor >bazel-archive-keyring.gpg \
&& echo "deb [arch=amd64 signed-by=/usr/share/keyrings/bazel-archive-keyring.gpg] https://storage.googleapis.com/bazel-apt stable jdk1.8" | sudo tee /etc/apt/sources.list.d/bazel.list \
&& apt update \
&& apt full-upgrade \
&& apt install bazel \
&& wget https://mirrors.huaweicloud.com/bazel/5.1.1/bazel-5.1.1-installer-linux-x86_64.sh \
&& chmod +x bazel-5.1.1-installer-linux-x86_64.sh \
&& ./bazel-5.1.1-installer-linux-x86_64.sh \
&& echo 'export PATH="$PATH:$HOME/bin"' >> ~/.bashrc \
&& echo 'source /usr/local/lib/bazel/bin/bazel-complete.bash' >> ~/.bashrc \
&& rm -rf /var/lib/apt/lists/* \
&& apt-get clean \
&& rm -rf bazel-5.1.1-installer-linux-x86_64.sh 

CMD ["sleep infinity"]
