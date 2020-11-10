# Syno, a CLI wrapper for SMB shares

**DISCLAIMER**: This has only been tested on Mac OS X. Adapting for Linux should be quite straightforward though.

Mounting 

This is a wrapper tool for quickly seeing what SMB shares are avaible from your Synology (or SMB server), mount them and unmount them. I's a clear case of code as documentation, where I wrap and automate different commands involved in this just to only remember a couple of things.

## Some examples

Showing active configuration (Synology server, user, and configuration file):
```bash
syno config
```

Listing available shares:
```bash
syno shares
```

Mounting a share called `myvolume`:
```bash
syno mount -v myvolume
```

Listing mounted shares:
```bash
syno list
```

Unmounting the share:
```bash
syno unmount -v myvolume
```

or (to unmount all):
```bash
syno umount -a
```

Getting help:
```bash
syno -h
```

## Installation and set up

- Clone the project.
- Move the `syno` bash script somewhere where your `PATH` can reach it. I use `$HOME/bin`.
- Move the configuration file `syno_creds` somewhere where to typically put credentials or other configs. I use `$HOME/.config`.
- Edit the `syno_creds` and fill in the following variables:
    - `SYNO_USER`: your Synology user with permissions to access the shares.
    - `SYNO_PW`: user password.
    - `SYNO_ID`: This can either be the Synology IP or the Avahi name for the NAS.
    - `BASE_DIR`: location where you want your shares to be mounted. I use `$HOME/syno_mounts`.
- Protect your credentials file by changing its permissions:
    ```bash
    chmod 400 syno_creds
    ````

You should be good to go.
