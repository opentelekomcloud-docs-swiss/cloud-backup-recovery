:original_name: cbr_03_0016.html

.. _cbr_03_0016:

Creating an Image from a Cloud Server Backup
============================================

CBR allows you to create images using ECS backups. You can use the images to provision ECSs to rapidly restore service running environments.

You can also use server backups to create images and then provision servers to restore data if your servers were accidentally deleted.

Prerequisites
-------------

-  The following operations have been performed:

   -  The `Linux ECS is optimized <https://docs.sc.otc.t-systems.com/usermanual/ims/en-us_topic_0047501133.html>`__ and `Cloud-Init is installed <https://docs.sc.otc.t-systems.com/usermanual/ims/en-us_topic_0030730603.html>`__.
   -  The `Windows ECS is optimized <https://docs.sc.otc.t-systems.com/usermanual/ims/en-us_topic_0047501112.html>`__ and `Cloudbase-Init is installed <https://docs.sc.otc.t-systems.com/usermanual/ims/en-us_topic_0030730602.html>`__.

Notes
-----

-  Images created using a backup are the same, so CBR allows you to use a backup to create only one full-ECS image that contains the whole data of the system disk and data disks of the ECS, in order to save the image quota. After an image is created, you can use the image to provision multiple ECSs in a batch.
-  A backup with an image created cannot be deleted directly. To delete such a backup, delete its image first. If a backup is automatically generated based on a backup policy and the backup has been used to create an image, the backup will not be counted as a retained backup and will not be deleted automatically.
-  A backup is compressed when it is used to create an image, so the size of the generated image may be smaller than the backup size.

Constraints
-----------

-  You can create an image from a backup only when the backup is in the **Available** state or in the **Creating** state with "Image can be created" displayed.

   .. note::

      -  Once backup creation starts, the backup enters the **Creating** state. After a period of time, a message stating "Image can be created" is displayed under **Creating**. In this case, the backup can be used for creating an image, even though it is still being created and cannot be used for restoration.

-  The backup must contain the system disk data.
-  Only ECS backups can be used to create images.

Procedure
---------

#. Log in to the CBR console.

   a. In the upper left corner, click |image1| and select a region.
   b. Click |image2| and choose **Storage** > **Cloud Backup and Recovery**.

#. Click the **Backups** tab. Locate the desired backup. For details, see :ref:`Viewing a Backup <cbr_03_0013>`.

#. In the row of the backup, choose **More** > **Create Image**.


   **Figure 1** Creating an image

   |image3|

#. Create an image by referring to section "Creating a Full-ECS Image from a CBR Backup" in the *Image Management Service User Guide*.

#. Use the image to provision ECSs when needed. For details, see section "Creating an ECS from an Image" in the *Image Management Service User Guide*.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001599534545.jpg
.. |image3| image:: /_static/images/en-us_image_0000001186630558.png
