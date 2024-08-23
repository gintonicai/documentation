---
description: >-
  Section includes information on how to check the status of nodes provided by
  various contributors and instructions on accessing system logs for monitoring
  and troubleshooting purposes.
---

# Monitoring and Managing Your Node

## Check Node Status

The node status of all providers can be viewed on this [page](https://petals-monitor.sfxdx.com/). This feature is currently hosted on the Petals page, with the link subject to change in the future.

## Access Logs

The Distillery logs can be found at '_/root/distillery\_logs/script.log'_. These logs contain reference information about the various stages that the script goes through during execution, including:

* Installation of required dependencies
* Calculation of available video card memory
* Petals server startup
* Retrieval of the PeerID
* PID of the running Distillery server process
* Sending a request to the backend with the blockchain address and PeerID

In case of errors at any stage, they will be logged in the script log.

It's recommended to regularly check the logs to ensure that the script is running smoothly and to identify any potential issues.
