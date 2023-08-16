:original_name: cbr_05_0005.html

.. _cbr_05_0005:

Failed to Attach Disks
======================

Symptom
-------

Failed to attach disks despite following the procedure: Create EVS disks using the same disk backup (XFS file system backup) and attach them to the same server (to which multiple EVS disks with XFS file system backup have been attached). Running the **mount** command to attach disks fails.

Possible Cause
--------------

The superblock of an EVS disk (with XFS file systems) stores a universally unique identifier (UUID) about the file system. If a server has multiple disks (with XFS file systems), multiple UUIDs will exist on the server. Multiple disks may have the same UUID, which can cause the file system mounting to fail.

Troubleshooting Methods
-----------------------

When attaching an EVS disk, use parameters without UUID control or reallocate a new UUID to ensure that each UUID is unique.

Solution
--------

#. Log in to the server to which EVS disks failed to be attached.
#. Resolve the problem in either of the following ways:

   -  Use a parameter without UUID when attaching an EVS disk: Run **mount -o nouuid /dev/Device name** **/Mount path**, for example:

      **mount -o nouuid /dev/sda6 /mnt/aa**

   -  Reallocate a new UUID: Run **xfs_admin -U generate /dev/**\ *Device name*.

   .. note::

      Because setting a parameter without UUID requires you to execute the command every time, you are advised to reallocate a new UUID.
