# qgis4

The [qgis4](http://qgis4.qgis.org/) server is dedicated to QGIS Server for:
- Daily reports for OGC tests on WMS 1.3.0 and WFS 1.1.0
- Daily reports for performance tests
- Online instances for OGC certification process
- Demonstration of QWC2 applications

## Encrypted files

Some files in this directory are encrypted using [git-crypt](https://github.com/AGWA/git-crypt).  To
be able to read these files you have to have `git-crypt` installed, and you need to unlock the
repository using the following command:

```
$ git-crypt unlock
```

## Deployment

To deploy this project on a remote server, you have to:
- have a Unix user `qgis-server-admin` on the `qgis4` host
- configure your SSH to have a root connection without password (ssh key)
- create an alias in your `~/.ssh/config` for the host `qgis4` (for
  the `root` user or a sudo user)
- execute the Ansible playbook for the virtualenv (see below)


```
$ cd ansible
$ virtualenv venv
$ source venv/bin/activate
(venv)$ pip install -r requirements.txt
(venv)$ ./qgis4.sh
```

## URLs

Links:
- [QGIS Server 3.4 for OGC certification](http://qgis4.qgis.org:8080/certification_qgisserver_3_4?SERVICE=WMS&REQUEST=GetCapabilities)
- [QGIS Server Master for OGC certification](http://qgis4.qgis.org:8080/certification_qgisserver_master?SERVICE=WMS&REQUEST=GetCapabilities)
- [QWC2 demos](http://qgis4.qgis.org:8081/qwc2_demo/)
- [QGIS Server demo](http://qgis4.qgis.org:8081/qgisserver_demo/)
