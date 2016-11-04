Components
==========

Internal
--------
The following are internal components of commissaire.

.. todo::

    REST Interface -> commissaire-server

REST Interface
~~~~~~~~~~~~~~
The rest interface is the way an administrator works with commissaire. It
attempts to follow REST as strictly as possible through the interpretation of
commissaire developers.


Investigator
~~~~~~~~~~~~

.. todo::

    Rename to commissaire-investigator-service and update text.

The investigator is a subprocess which is tasked with investigating
and bootstrapping new host nodes. When a new host is added it's the
investigator which populates the host data in etcd and gets the right services
going on the new host.


.. todo::

    Add commissaire-storage-service


.. todo::

    Add commissaire-clusterexec-service


External
--------
The following are external components of commissaire.

etcd
~~~~
etcd is used as the data store for commissaire. Any persistent data is kept
within etcd as either traditional *key* = *value* pairs or as *key* = *JSON*. While
any etcd instance will work it's recommended to use the same etcd cluster with
Kubernetes.

Container Manager
~~~~~~~~~~~~~~~~~
OpenShift or Kubernetes can be used as the container manager. commissaire utilizes
Kubernetes API to ensure that new host nodes register properly. From this point
forward Kubernetes is able to use the host node to schedule pods, etc...
