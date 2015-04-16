# ceilometer_sriov_counters
Plugin for Ceilometer SRIOV traffic counters

#### Table of Contents

1. [Overview - What is the Ceilometer SRIOV traffic counters plugin?](#overview)
2. [Module description - What does the module do?](#module-description)
3. [Prerequisites - The basics to work with the plugin](#prerequisites)
4. [Configuration - How to configure the plugin?](#configuration)
5. [Description of the traffic counters](#description-of-the-traffic-counters)
6. [Show the traffic counters](#show-the-traffic-counters)

Overview
--------

The Ceilometer SR-IOV traffic counters allows the ceilometer to inspect the traffic counters of the SR-IOV VM.

Module description
------------------

The ceilometer libvirt inspector looks for the an interface that is binded to the VM.
The VM that is connected via SR-IOV does not create such interface therefore the libvirt inspector ignores it.
The Ceilometer SR-IOV traffic counters plugin looks for the VM connected with SR-IOV. Then it acquire the counters from the driver and pass the counters to the ceilometer inspector.

Prerequisites
-------------

  *	Supported OS: RH6.X RH7.X
  *	OpenStack supported versions: Valid from Juno and onward.
  *	Other requirements if exists: SRiov enable

Installation
-------------

  *	To install the module, install the rpm file. There are no configurable parameters.

Description of the traffic counters
-----------------------------------
These are the supported traffic counters.

  * network.outgoing.bytes
  * network.incoming.bytes
  * network.outgoing.packets
  * network.incoming.packets

Shoing the traffic counters
---------------------------

  * From openstack horizon: go to admin -> resource Usage and then query for the counters.
  * From cli run: ceilometer  statistics -m  (counter_name)

  ```
  for example: ceilometer  statistics -m network.outgoing.bytes
  ```

