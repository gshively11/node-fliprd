node-fliprd
===========

Client for flipr powered by etcd.  Configuration and feature flipping in a distributed environment.

#Work in Progress (Notes)
##Configuration specific to fliprd (most of flipr config is still needed)
* `host` etcd host
* `port` etcd port
* `key` key that is storing config
* `retryInterval` the number of seconds to wait between connection attempts if etcd dies

##Behavior
fliprd does the same thing as flipr, except instead of reading local yaml files, it grabs the config from etcd.  It also listens for changes to etcd and automatically loads the new config.  It still has the same behavior as flipr in terms of config and feature flipping using custom rules.
* If etcd dies, it will continue to use the last config received
