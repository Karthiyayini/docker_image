 ====================================================================== #
# Android SDK Docker Image (VNC enabled)
# ====================================================================== #

# Base image
# ---------------------------------------------------------------------- #
FROM thyrlian/android-sdk:latest

# Author
# ---------------------------------------------------------------------- #
LABEL maintainer "thyrlian@gmail.com"

# install and configure VNC server
ENV USER root
ENV DISPLAY :1
EXPOSE 5901
ADD vncpass.sh /tmp/
ADD supervisord_vncserver.conf /etc/supervisor/conf.d/
RUN apt-get update -y && \
    apt-get install -y --no-install-recommends xfce4 xfce4-goodies xfonts-base tightvncserver expect && \
    chmod +x /tmp/vncpass.sh; sync && \
    /tmp/vncpass.sh && \
rm /tmp/vncpass.sh && \
