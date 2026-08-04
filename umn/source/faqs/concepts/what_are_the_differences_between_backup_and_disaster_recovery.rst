:original_name: cbr_06_0004.html

.. _cbr_06_0004:

What Are the Differences Between Backup and Disaster Recovery?
==============================================================

The following table lists the key differences between backup and disaster recovery (DR).

.. table:: **Table 1** Differences between backup and DR

   +----------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Item     | Backup                                                                                                                                                           | DR                                                                                                                                                                                                                                                                                                                                        |
   +==========+==================================================================================================================================================================+===========================================================================================================================================================================================================================================================================================================================================+
   | Purpose  | To prevent data loss. It adopts the snapshot or backup techniques to generate data backups that can be used to restore data when data loss or corruption occurs. | To ensure service continuity. It takes the replication techniques (such as application-layer replication, host-based replication at the I/O layer, and storage-layer replication) to construct standby service hosts and data in a remote center, so that the remote center can take over services whenever the primary center is faulty. |
   +----------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Scenario | It offers protection against virus attacks, accidental deletions, software and hardware faults.                                                                  | It enables failover upon software and hardware faults, as well as natural disasters, such as tsunami, fires, and earthquakes, to fast recover services. When the source AZ recovers, you can easily fail back to the source AZ.                                                                                                           |
   +----------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Cost     | The cost is approximately 1% to 2% of the production system's cost.                                                                                              | The cost is 20% to 100% of the production system's cost, depending on the required RPO and RTO levels. In an active-active DR architecture, the service system deployed at the standby site must be identical to that of the active site, which doubles the infrastructure cost.                                                          |
   +----------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. note::

   Recovery Point Objective (RPO) defines the maximum acceptable amount of data loss measured in time.

   Recovery Time Objective (RTO) specifies the maximum acceptable amount of time required to restore the entire system after a disaster.
