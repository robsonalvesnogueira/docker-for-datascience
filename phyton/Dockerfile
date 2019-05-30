FROM python:3.7-alpine

# Adicionar git para permitir clonar repositórios. Ex. Oh My Zsh
RUN apk add git

# Adicionar Zsh
RUN apk add zsh

# Adicionar Oh My Zsh
RUN sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"