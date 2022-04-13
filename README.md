# sensibility
Performs a census of a cluster’s nodes, scores the cluster out of 100 for diverseness

This asks cluster nodes to self-report aspects of their software and hardware configuration, such as:

## type
* Processor maker
* Processor model
* RAM generation
* SSL library used
* OS type
* Kernel version
* OS version

## capacity
* RAM capacity
* Disk capacity

## reliability
* Is the RAM ECC?
* How long have the components been, or otherwise likely been, in operation?
* System uptime
* App uptime

## security
* Is the processor patched for Meltdown/Spectre?
* Are management engines blocked off

### Notes

For type and capacity, newer and more is not necessarily better since it would be generally preferable for nodes to reach their performance or size limits and varying times from each other.

Security is generally preferable to keep up-to-date as possible since there may be latent issues or simply trustedness, where compromise of one node can lead to loss of the other nodes. If the other aspects are as disparate as possible then security fixes themselves will be different, so less likely to suffer the same kinds of reliabilty failures.

Caveat, it is best to stagger patching times a little.

The polling software should run and query at very different t8mes on each node to limit the possibility of causing failure across multiple nodes at the same time.
