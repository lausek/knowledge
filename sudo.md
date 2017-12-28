# Enable sudo for user

Add user to sudo group

    useradd -G sudo <user>

# Disable password for sudo

Change line in `/etc/sudoers` to
    
    %sudo   ALL=(ALL) NOPASSWD:ALL
