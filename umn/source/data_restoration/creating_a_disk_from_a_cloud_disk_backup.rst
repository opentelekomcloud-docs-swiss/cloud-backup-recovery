:original_name: cbr_03_0017.html

.. _cbr_03_0017:

Creating a Disk from a Cloud Disk Backup
========================================

You can use a disk backup to create a disk that contains the same data as the backup.

Disks created using system disk backups can only be used as data disks on servers. They cannot be used as system disks.

Procedure
---------

#. Log in to the CBR console.

   a. In the upper left corner, click |image1| and select a region.
   b. Click |image2| and choose **Storage** > **Cloud Backup and Recovery**.

#. Click the **Backups** tab. Locate the desired backup. For details, see :ref:`Viewing a Backup <cbr_03_0013>`.

#. Click **Create Disk** in the **Operation** column of the backup. The button is available only when the backup status is **Available**. The **Create Disk** page is displayed.


   .. figure:: /_static/images/en-us_image_0000001186472170.png
      :alt: **Figure 1** Create Disk

      **Figure 1** Create Disk

#. Configure the disk parameters.

   See the parameter description table in section "Create an EVS Disk" of the *Elastic Volume Service User Guide*.

   Pay attention to the following:

   -  You can choose the AZ to which the backup source disk belongs, or a different AZ.

   -  The new disk must be at least as large as the backup's source disk.

      If the capacity of the new disk is greater than that of the backup's source disk, format the additional space by following the steps provided in section "Extending Disk Partitions and File Systems" of the *Elastic Volume Service User Guide*.

   -  You can create a disk of any type regardless of the backup's source disk type.

#. Click **Create Now**.

#. Go back to the disk list. Check whether the disk is successfully created.

   You will see the disk status progress through the following phases: Creating → Available → Restoring → Available. Because Instant Restore is supported, the **Restoring** phase may be very brief and easy to miss. When the status changes from **Creating** to **Available**, the disk has been successfully created. When the status changes from **Restoring** to **Available**, the backup data has been successfully restored to the disk.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001599534545.jpg
