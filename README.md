# Precompiled CouchDB v3.1.1 for Raspberry pi 3

## How I compiled CouchDB
I downloaded the CouchDB tarball from the official link

https://www.apache.org/dyn/closer.lua?path=/couchdb/source/3.1.1/apache-couchdb-3.1.1.tar.gz

I deflated the tarball on my Raspberry PI3 on which I installed the official Raspberry OS 

https://www.raspberrypi.org/software/operating-systems/#raspberry-pi-os-32-bit

and I followed the instructions in the official documentation for the installation from source

https://docs.couchdb.org/en/stable/install/unix.html#installation-from-source

the Raspberry OS is in fact a Debian buster

```
cat /etc/os-release 
PRETTY_NAME="Raspbian GNU/Linux 10 (buster)"
NAME="Raspbian GNU/Linux"
VERSION_ID="10"
VERSION="10 (buster)"
VERSION_CODENAME=buster
ID=raspbian
ID_LIKE=debian
HOME_URL="http://www.raspbian.org/"
SUPPORT_URL="http://www.raspbian.org/RaspbianForums"
BUG_REPORT_URL="http://www.raspbian.org/RaspbianBugs"
```

The compilation was straightforward and the result is contained in the tarball 

```couchdb_v3.1.1_raspberry_os_5.4_kernel.tgz```

## CouchDB installation

Once you compiled CouchDB by yourself or downloaded the precompiled tarball, you can jump directly to the *'1.1.5. User Registration and Security'* paragraph of the installation section. 

In this section you will be guided to install CouchDB into the user home `/home/couchdb`.

Before the first run you have to define the `admin` user.

In order to do so you have to login as `couchdb` user, open the file `/home/couchdb/etc/local.ini` and insert the password for the `admin` user in the section `[admins]`

You can find more details in the official instructions at the link https://docs.couchdb.org/en/stable/config/auth.html#config-admins

Now you are ready for the first run.

## First run and configuration

Once your CouchDB is up and running for the first run, you have to login as `admin` at the web interface and add two databases named `_users` and `_replicator`.

The first is needed to add regular users and the second to register replication actions.

### Configuring regular user

To add a regular user to a db you added follow this link https://stackoverflow.com/questions/3684749/creating-regular-users-in-couchdb


## Running CouchDB as a systemd service

In order to run CouchDB as system service:
* gain root privileges 
* copy the file `couchdb.service` in the folder `/etc/systemd/system`
* enable CouchDB as service with `systemctl enable couchdb`
* start CouchDB with `systemctl start couchdb`
* and finally verify it with `systemctl status couchdb`

**Now its time to relax!**


