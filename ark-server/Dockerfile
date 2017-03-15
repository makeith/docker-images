FROM ubuntu:16.04

# Initial Environment Setup
RUN apt-get -y update                             && \
    apt-get -y install lib32gcc1 wget             && \
    echo "fs.file-max=100000" >> /etc/sysctl.conf && \
    sysctl -p /etc/sysctl.conf                    && \
    mkdir /install-media                          && \
    mkdir /server                                 && \
    echo "*               soft    nofile          1000000" >> /etc/security/limits.conf && \
    echo "*               hard    nofile          1000000" >> /etc/security/limits.conf

# Install Steam and Update Ark
WORKDIR /install-media
RUN \
    wget https://steamcdn-a.akamaihd.net/client/installer/steamcmd_linux.tar.gz && \
    tar -xvzf steamcmd_linux.tar.gz                                             && \
    ./steamcmd.sh +login anonymous +force_install_dir /server +app_update 376030 +quit

# Create User
RUN groupadd -g $PGID ark && \
    useradd -u $PUID -g $PGID ark

# Cleanup
rm -r /install-media

#Expose the port
EXPOSE 34777/udp 27015/udp
VOLUME /server

# Start Server
USER $PUID
CMD ./ShooterGameServer TheIsland?listen?SessionName=$SERVER_NAME?ServerPassword=$SERVER_PASSWORD?ServerAdminPassword=$SERVER_ADMIN_PASSWORD -server -log