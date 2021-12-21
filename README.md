# GoByte Ninja Back-End (gobyteninja-be)
Forked from dashninja By Alexandre (aka elbereth) Devilliers

Check the running live website at https://www.masternodes.gobyte.network

This is part of what makes the GoByte Ninja monitoring application.
It contains:
- Private REST API (using PHP and Phalcon framework)

## Requirement:
* You will need a running website, official at https://masternodes.gobyte.network uses nginx

For the REST API:
* PHP v5.6 with mysqli
* Phalcon v2.0.x (should work with any version)
* MySQL database with GoByte Ninja Database (check gobyteninja-db repository)

## Optional:
* GoByte Ninja Control script installed and running (to feed the database through this API)

## Install:
* Go to the root of your website for GoByte private API (ex: cd /home/gobyteninja/cmd/)
* Get latest code from github:
```shell
git clone https://github.com/gobytecoin/gobyteninja-be.git
```

* Configure php to answer only to calls to api/index.php rewriting to end-point api/

## Configuration:
The initial idea was to be able to have a central application (gobyteninja-be) where one or several hub of nodes connect to in order to provide monitoring.

Current implementation takes as assumption that there is only one hub configured (there can be several nodes).

Identification of this app and possible hubs are done with SSL certificates and it was designed to run on IPv6 only.
You need to configure your web server (GoByte Ninja official uses nginx) with your CA and create client certificates to trusted hubs to connect to it.

Once the server is configured correctly import the client certificate CN into cmd_hub to give access to that hub (this can be a remote host or ::1). Both the certificate and IPv6 are checked to match and give access.

Rest of documentation is not done yet (if ever).
