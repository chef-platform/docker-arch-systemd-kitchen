docker-arch-systemd-kitchen
===========================

Docker image for an ArchLinux with a working Systemd (working without
--privileged), provisionned with Chef to be used in Test Kitchen.

Test it easily with:

    # Get the image
    docker pull chefplatform/arch-systemd-kitchen
    # Run it (do not forget cgroup volume for systemd)
    docker run -d -v /sys/fs/cgroup:/sys/fs/cgroup:ro --name ask \
      chefplatform/arch-systemd-kitchen
    # Open a shell in it, you can try 'systemctl' for instance
    docker exec -it ask bash -c 'TERM=xterm bash'
    # Kill and remove the container
    docker kill ask; docker rm ask
