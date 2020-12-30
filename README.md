# ubiquiti_unifi_network

Vagrantfile for Ubiquiti UniFi Network

## Vagrant

* Create and configure Ubiquiti UniFi Network guest machine. If asked for a bridged network interface, select the one conntected to the network you want to configure.

  ```Shell
  vagrant up
  ```

* Now you have to wait some minutes for your installation to be completed.

## Setup Ubiquiti UniFi Network

* Use the URL you got provided to configure Ubiquiti UniFi Network: https://$IP-ADDRESS:8443

* Because self signed certificates are used, you might need to accept some browser warnings.

* `Name Your Controller`, agree the `end user license agreement` and select `Next`.

* Switch to `Advanced Setup`.

* Disable `Enable Remote Access` and `Use your Ubiquiti account for local access`.

* Create an account by providing requested details and select `Next`.

* Finish setup.
