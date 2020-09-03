FROM centos:7.2.1511

# install packages required chromium
RUN yum install -y git unzip
RUN yum install -y pango.x86_64 \
  libXcomposite.x86_64 \
  libXcursor.x86_64 \
  libXdamage.x86_64 \
  libXext.x86_64 \
  libXi.x86_64 \
  libXtst.x86_64 \
  cups-libs.x86_64 \
  libXScrnSaver.x86_64 \
  libXrandr.x86_64 \
  GConf2.x86_64 \
  alsa-lib.x86_64 \
  atk.x86_64 \
  gtk3.x86_64 \
  ipa-gothic-fonts \
  xorg-x11-fonts-100dpi \
  xorg-x11-fonts-75dpi \
  xorg-x11-utils \
  xorg-x11-fonts-cyrillic \
  xorg-x11-fonts-Type1 \
  xorg-x11-fonts-misc
RUN yum update -y nss

# install chromium
RUN git clone https://github.com/scheib/chromium-latest-linux.git
RUN ./chromium-latest-linux/update.sh

# set environment variable
ENV CHROME_PATH /chromium-latest-linux/latest/chrome

# install node
RUN curl -sL https://rpm.nodesource.com/setup_12.x | bash -
RUN yum install -y nodejs

# install lighthouse
RUN npm install -g lighthouse@6.3.0

# add user
RUN useradd lighthouse
USER lighthouse

WORKDIR /lighthouse
