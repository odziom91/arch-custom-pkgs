FROM archlinux:latest

# add chaotic-aur
RUN pacman-key --init \
    && pacman-key --recv-key 3056513887B78AEB --keyserver keyserver.ubuntu.com \
    && pacman-key --lsign-key 3056513887B78AEB \
    && echo -e "\n[chaotic-aur]\nSigLevel = Never\nServer = https://cdn-mirror.chaotic.cx/chaotic-aur/\$arch" >> /etc/pacman.conf

# prepare environment for makepkg
RUN pacman -Sy --noconfirm \
    base base-devel git sudo python \
    && pacman -Scc --noconfirm

# create non-root user bobthebuilder
ARG USERNAME=bobthebuilder
RUN useradd -m -u 1001 $USERNAME

# prepare build directory for non-root user
RUN mkdir -p /home/$USERNAME/build && chown bobthebuilder:bobthebuilder /home/$USERNAME/build

# set user and workdir
USER $USERNAME
WORKDIR /home/$USERNAME/build