FROM zenika/alpine-chrome:with-node

USER root

# 安装 agent-browser CLI
RUN npm install -g agent-browser

# 指向镜像里已有的 Chromium,避免它再去下载 Chrome
ENV AGENT_BROWSER_EXECUTABLE_PATH=/usr/bin/chromium-browser

# 用非 root 用户跑(镜像自带 chrome 用户)
USER chrome
WORKDIR /home/chrome
RUN agent-browser install
ENTRYPOINT ["agent-browser"]
CMD ["--help"]
