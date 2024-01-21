FROM ghcr.io/isaacsancheza/selenium:latest

# set locale
ENV LANG=es_MX.UTF-8  
ENV LC_ALL=es_MX.UTF-8   
ENV LANGUAGE=es_MX:es  

RUN apt-get update  \
    && export DEBIAN_FRONTEND=noninteractive \
    #
    # installl locales 
    && apt-get install -y --no-install-recommends locales \
    #
    # clean-up
    && apt-get autoremove -y  \
    && apt-get clean -y  \
    && rm -rf /var/lib/apt/lists/* /tmp/library-scripts

# gen locale
RUN sed -i '/es_MX.UTF-8/s/^# //g' /etc/locale.gen \
    && locale-gen
