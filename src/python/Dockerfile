ARG BASE_IMAGE=python
ARG QUARTOVERSION=1.5.56
ARG VARIANT=3.12-bookworm
FROM ${BASE_IMAGE}:${VARIANT}

# install requirements
COPY assets/requirements.txt /tmp/pip-tmp/
RUN pip3 --disable-pip-version-check --no-cache-dir install -r /tmp/pip-tmp/requirements.txt \
    && rm -rf /tmp/pip-tmpf

# # # quarto update
ARG QUARTOVERSION
RUN cd /usr/share/ \
    && wget https://github.com/quarto-dev/quarto-cli/releases/download/v${QUARTOVERSION}/quarto-${QUARTOVERSION}-linux-amd64.tar.gz \
    && tar -xvzf quarto-${QUARTOVERSION}-linux-amd64.tar.gz && mv quarto-${QUARTOVERSION} .quarto \
    && rm /usr/local/bin/quarto \
    && ln -s .quarto quarto

ENV PATH "$PATH:/usr/share/quarto/bin"
