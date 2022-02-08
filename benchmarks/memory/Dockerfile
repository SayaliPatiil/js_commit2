FROM node:14-buster
ENV NODE_ENV=production
ENV CI=1
ENV GATSBY_CPU_COUNT=4
RUN apt-get update -y && apt-get upgrade -y && apt-get install git curl npm -y
RUN npm i -g gatsby-cli gatsby-dev-cli
WORKDIR /usr/src/app
RUN echo "\n\necho \"Welcome to the Gatsby Memory benchmark container!\\n  - /usr/src/gatsby : Your local gatsby repo\\n  - /usr/src/app : The memory benchmark gatsby site\\n\"" > /root/.bashrc

# set up gatsby-dev
RUN gatsby-dev --set-path-to-repo /usr/src/gatsby

# keep the process running
ENTRYPOINT ["tail", "-f", "/dev/null"]