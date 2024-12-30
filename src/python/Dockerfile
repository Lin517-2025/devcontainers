ARG BASE_IMAGE=python
# ARG QUARTOVERSION=1.5.56
ARG VARIANT=3.12-bookworm
FROM ${BASE_IMAGE}:${VARIANT}

# install requirements
COPY assets/requirements.txt /tmp/pip-tmp/
RUN pip3 --disable-pip-version-check --no-cache-dir install -r /tmp/pip-tmp/requirements.txt \
    && rm -rf /tmp/pip-tmpf

# allow pip install
# ENV PIP_TARGET=/usr/local/pip-global
# ENV PYTHONPATH=${PIP_TARGET}:${PYTHONPATH}
# ENV PATH=${PIP_TARGET}/bin:${PATH}
# RUN if ! cat /etc/group | grep -e "^pip-global:" > /dev/null 2>&1; then groupadd -r pip-global; fi \
#     && usermod -a -G pip-global vscode \
#     && umask 0002 && mkdir -p ${PIP_TARGET} \
#     && chown :pip-global ${PIP_TARGET} \
#     && ( [ ! -f "/etc/profile.d/00-restore-env.sh" ] || sed -i -e "s/export PATH=/export PATH=\/usr\/local\/pip-global:/" /etc/profile.d/00-restore-env.sh )


# rstudio preferences
# and .Rprofile
# COPY --chown=rstudio:rstudio assets/rstudio-prefs.json /home/rstudio/.config/rstudio/
# COPY --chown=rstudio:rstudio assets/.Rprofile /home/rstudio/
# COPY --chown=rstudio:rstudio assets/keybindings/ /home/rstudio/.config/rstudio/keybindings/
# COPY assets/.rpackages /home/rstudio/.rpackages

# # rust
# RUN apt-get install -y \
#     build-essential \
#     curl

# # Update new packages
# RUN apt-get update

# Get Rust
# RUN curl https://sh.rustup.rs -sSf | bash -s -- -y

# RUN echo 'source $HOME/.cargo/env' >> $HOME/.bashrc



# # # quarto update
# ARG QUARTOVERSION
# RUN cd /usr/share/ \
#     && wget https://github.com/quarto-dev/quarto-cli/releases/download/v${QUARTOVERSION}/quarto-${QUARTOVERSION}-linux-amd64.tar.gz \
#     && tar -xvzf quarto-${QUARTOVERSION}-linux-amd64.tar.gz && mv quarto-${QUARTOVERSION} .quarto \
#     && rm /usr/local/bin/quarto \
#     && ln -s .quarto quarto

# ENV PATH "$PATH:/usr/share/quarto/bin"
