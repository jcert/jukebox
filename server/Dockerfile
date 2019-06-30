FROM node:11.3.0

RUN apt-get update
RUN apt-get install -y \
  mpv \
  python3

RUN wget https://yt-dl.org/downloads/latest/youtube-dl -O /usr/local/bin/youtube-dl
RUN chmod a+rx /usr/local/bin/youtube-dl
RUN export PATH="$PATH:/usr/local/bin/"

RUN apt-get update && \
    apt-get install -y vlc-nox apt-utils alsa-utils nano pulseaudio && \
    usermod -a -G audio root && \
    usermod -a -G pulse-access root


COPY . /app
WORKDIR /app

RUN yarn

CMD ["yarn", "start"]
