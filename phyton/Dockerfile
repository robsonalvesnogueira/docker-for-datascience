FROM python:3.7-alpine

# Adicionar git para permitir clonar repositórios. Ex. Oh My Zsh
RUN apk add git

# Adicionar Zsh
RUN apk add zsh

# Adicionar Oh My Zsh
RUN sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"

# library for processing XML and HTML
RUN apk add --update --no-cache g++ gcc libxslt-dev
RUN pip install lxml
RUN pip install html5lib
RUN pip install beautifulsoup4

# A little word cloud generator in Python
RUN apk add jpeg-dev zlib-dev freetype-dev lcms2-dev openjpeg-dev tiff-dev tk-dev tcl-dev
RUN pip install wordcloud
RUN pip install matplotlib