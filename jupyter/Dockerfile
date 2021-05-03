FROM jupyter/datascience-notebook:lab-3.0.12
USER root
ENV NB_UID=500 \
	NB_GID=500 \
	GRANT_SUDO=yes \
	JUPYTER_ENABLE_LAB=yes \
	RESTARTABLE=yes
# Sets the file browser to show the whole home directory.
WORKDIR /home
