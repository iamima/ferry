FROM $USER/ferry-base
NAME gluster

# Create necessary directories
RUN mkdir -p /service/data /service/logs /service/sbin;chown -R ferry:docker /service/data;chown -R ferry:docker /service/logs

# Add the latest stable GlusterFS repo
RUN apt-get --yes install software-properties-common;add-apt-repository --yes ppa:semiosis/ubuntu-glusterfs-3.4

# Tell apt to use the latest repo packages. 
RUN echo "Package: *" >> /etc/apt/preferences
RUN echo "Pin: release o=LP-PPA-semiosis-ubuntu-glusterfs-3.4,a=quantal" >> /etc/apt/preferences
RUN echo "Pin-Priority: 900" >> /etc/apt/preferences

# Download the various packages needed
RUN apt-get update; apt-get --yes install git glusterfs-common glusterfs-client glusterfs-server attr

# Add the control script to the image. 
ADD ./startnode /service/sbin/
RUN chmod a+x /service/sbin/startnode

# Run the ssh daemon in the foreground (Docker does
# like daemons running in background)
CMD ["/service/sbin/startnode", "init"]
