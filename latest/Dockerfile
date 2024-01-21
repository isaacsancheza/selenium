FROM python:3.12-slim

ARG USERNAME=selenium
ARG USER_UID=1000
ARG USER_GID=$USER_UID

RUN apt-get update  \
    && export DEBIAN_FRONTEND=noninteractive \
    #
    # installl selenium requirements 
    && apt-get install -y --no-install-recommends xvfb chromium-driver \
    #
	# add non-root user
	&& groupadd --gid $USER_GID $USERNAME \
    && useradd -s /bin/zsh --uid $USER_UID --gid $USER_GID -m $USERNAME \
	#
    # clean-up
    && apt-get autoremove -y  \
    && apt-get clean -y  \
    && rm -rf /var/lib/apt/lists/* /tmp/library-scripts
