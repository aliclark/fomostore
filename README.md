# fomostore

A master-master node cluster which replicates data.

A write is considered successful if k+1 nodes have accepted the data in memory, where k is maximum simultaneous failures.

fomostore is intended to be simple and implemented several times with diverging methods, so that a heterogenous cluster has minimal chances for simultaneous failure,
and thus can more realistically accept a write without having sync'd the data to disk.

A related project [[aliclark/sensibility]] is intended to help understand how diverse a cluster's makeup is.

This distributed system is intended to be used as a building block, along with vanilla Raft, for building a distributed system.

Run your application code in duplicate on nodes in 2 or more availability zones (ensure that all effectful operations are idempotent and at-most-once),
and use Raft to help decide what to do next, based on the data present in fomostore.
