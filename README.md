# incognitum

## Features

* **One touch, three minute install**
* **Set-it-and-forget-it backups** will automatically run a backup of all your sites every night and email you in case of failure
* Works with **both Docker / Non-Docker installation types** [not yet implemented / work in progress]
* Stores backups both **locally and remotely [on S3]**
* **Encrypts** all remote backups with a 42 character passphrase
* **Requires no configuration inside Mastodon and/or Docker**, everything happens on the filesystem level completely unbeknownst to the application / containers themselves.
* Performs a **test restore** before every S3 backup to **ensure remote backup integrity and passphrase match**
* Allows you to restore your backup with **one single command** and a maximum of **three minutes of your time** even from a blank machine you've never set up before [not yet implemented / work in progress]
* **Perfectly restores every aspect of the Mastodon instance you're hosting**, from your database, to all of your files
* Outputs clean and colorful logs and stores them automatically inside its own log directory

## Install [or update / re-install] [tested on Ubuntu 18]

```
[log in as root on your Mastodon server]
cd
```

```
apt update
apt -y install git
```
```
git clone https://github.com/openspace42/incognitum
bash incognitum/setup
```

## Backing up

### Run backup script manually

```
bash openspace42/incognitum/tools/incognitum-backup
```

### Confirm automatic daily run via cron is working

```
cat logs/incognitum-backup/latest-log
```

## Restoring [not yet implemented / work in progress]

### Preparation [only if this is a new machine]

1. Run the installer as detailed above in the "Install" section

### Actually restoring

```
bash openspace42/incognitum/tools/incognitum-restore
```
