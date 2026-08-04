:original_name: cbr_03_0005.html

.. _cbr_03_0005:

Dissociating Resources from a Vault
===================================

If you no longer need to back up an associated resource, dissociate it from your vault.

.. warning::

   After a resource is dissociated from a vault, the vault's backup policy no longer applies to the resource. In addition, **all manual and automatic backups of this resource will be deleted. Deleted backups cannot be used to restore data anymore**.

Dissociating a resource from a vault does not impact the performance of the services that use the resource.

Procedure
---------

#. Log in to the CBR console.

   a. In the upper left corner, click |image1| and select a region.
   b. Click |image2| and choose **Storage** > **Cloud Backup and Recovery**.

#. Locate the target vault and click its name.

#. In this example, cloud servers will be used as an example to illustrate the process. Click the **Associated Servers** tab. Find the target server and click **Dissociate** in the **Operation** column. See :ref:`Figure 1 <cbr_03_0005__fig1376320199159>`.

   .. _cbr_03_0005__fig1376320199159:

   **Figure 1** Dissociating a server

   |image3|

#. Confirm the information and click **OK**.

   After the dissociation, the result is displayed in the upper right corner. If the target server is not displayed in the **Associated Servers** list, the dissociation is successful.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001599534545.jpg
.. |image3| image:: /_static/images/en-us_image_0000002057589729.png
