===================
Computational modes
===================

.. _Batch:

-----
Batch
-----

In the batch processing mode, the algorithm works with the entire data set to produce the final
result. A more complex scenario occurs when the entire data set is not available at the moment
or the data set does not fit into the device memory.

.. _Online:

------
Online
------

In the online processing mode, the algorithm processes a data set in blocks streamed into the
device's memory. Partial results are updated incrementally and finalized when the last data block
is processed.

.. _Distributed:

-----------
Distributed
-----------

In the distributed processing mode, the algorithm operates on a data set distributed across
several devices (compute nodes). On each node, the algorithm produces partial results that
are later merged into the final result on the master node.