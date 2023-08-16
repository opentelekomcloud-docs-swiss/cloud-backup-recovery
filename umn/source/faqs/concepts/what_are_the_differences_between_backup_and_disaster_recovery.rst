:original_name: cbr_06_0004.html

.. _cbr_06_0004:

What Are the Differences Between Backup and Disaster Recovery?
==============================================================

The following table lists the main differences between backup and disaster recovery (DR).

.. table:: **Table 1** Differences between backup and DR

   +----------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Item     | Backup                                                                                                                                                           | DR                                                                                                                                                                                                                                                                                                                                        |
   +==========+==================================================================================================================================================================+===========================================================================================================================================================================================================================================================================================================================================+
   | Purpose  | To prevent data loss. It adopts the snapshot or backup techniques to generate data backups that can be used to restore data when data loss or corruption occurs. | To ensure service continuity. It takes the replication techniques (such as application-layer replication, host-based replication at the I/O layer, and storage-layer replication) to construct standby service hosts and data in a remote center, so that the remote center can take over services whenever the primary center is faulty. |
   +----------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Scenario | It offers protection against virus attacks, accidental deletions, software and hardware faults.                                                                  | It enables failover upon software and hardware faults, as well as natural disasters, such as tsunami, fires, and earthquakes, to fast recover services. When the source AZ recovers, you can easily fail back to the source AZ.                                                                                                           |
   +----------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Cost     | The cost is 1 to 2% of the production system's cost.                                                                                                             | The cost is 20 to 100% of the production system's, varying with the RPO/RTO requirements. For active-active DR, the service system deployed in the standby center is required to be the same as that in the active system. In this case, the cost on infrastructure doubles.                                                              |
   +----------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. note::

   Recovery Point Objective (RPO) specifies the maximum acceptable period in which data can be lost.

   Recovery Time Objective (RTO) specifies the maximum acceptable amount of time for restoring the entire system after a disaster occurs.
