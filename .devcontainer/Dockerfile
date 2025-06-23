FROM mcr.microsoft.com/devcontainers/ruby:3.2

# Install dependencies for Jekyll and GitHub Pages
RUN apt-get update && \
    apt-get install -y build-essential libffi-dev libyaml-dev zlib1g-dev && \
    gem install bundler
