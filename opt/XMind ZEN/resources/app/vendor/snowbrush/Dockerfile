FROM node:8.9.1-alpine

ARG RSA_KEY

RUN \
  apk update && \
  apk add openssh && \
  apk update && \
  apk add git && \
  mkdir -p ~/.ssh && \
  echo "${RSA_KEY}" >> ~/.ssh/snowbrush && \
  chmod 0400 ~/.ssh/snowbrush && \
  git config --global core.sshCommand "ssh -i ~/.ssh/snowbrush -o UserKnownHostsFile=/dev/null -o StrictHostKeyChecking=no -o IdentitiesOnly=yes -F /dev/null" && \
  git config --global core.autocrlf input && \
  git config --global core.autocrlf input && \
  git config --global user.name "snowbrush-builder" && \
  git config --global user.email "snowbrush-builder@xmind.net"