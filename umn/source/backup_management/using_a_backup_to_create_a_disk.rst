:original_name: cbr_03_0017.html

.. _cbr_03_0017:

Using a Backup to Create a Disk
===============================

You can use a disk backup to create a disk. After the disk is created, data on the new disk is the same as that in the disk backup.

After a new disk is created using the backup data of a system disk, the new disk can only be mounted to the cloud server as a data disk and cannot be mounted as a system disk.

Procedure
---------

#. Log in to CBR Console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select your region and project.
   c. Choose **Storage** > **Cloud Backup and Recovery**. Select a backup tab from the left navigation pane.

#. Click the **Backups** tab. Locate the desired backup. For details, see :ref:`Querying a Backup <cbr_03_0013>`.

#. If the status of the target backup is **Available**, click **Create Disk** in the **Operation** column of the backup.


   .. figure:: /_static/images/en-us_image_0000001186472170.png
      :alt: **Figure 1** Create Disk

      **Figure 1** Create Disk

#. Set the disk parameters.

   .. note::

      For details about these parameters, see the parameter description table in section "Creating an EVS Disk" of the *Elastic Volume Service User Guide*.

      Note the following items when setting disk parameters:

      -  You can choose the AZ to which the backup source disk belongs, or you can choose a different AZ.

      -  The new disk must be at least as large as the backup's source disk.

         If the capacity of the new disk is greater than that of the backup source disk, initialize the disk by following the steps provided in section "Extending Disk Partitions and File Systems" of the *Elastic Volume Service User Guide*.

      -  You can create a disk of any type regardless of the backup's disk type.

#. Click **Next**.

#. Go back to the disk list. Check whether the disk is successfully created.

   You will see the disk status change as follows: **Creating**, **Available**, **Restoring**, **Available**. If Instant Restore is supported, you may not notice the **Restoring** status because the restoration speed is very fast. After the disk status has changed from **Creating** to **Available**, the disk is successfully created. After the status has changed from **Restoring** to **Available**, backup data has been successfully restored to the created disk.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
