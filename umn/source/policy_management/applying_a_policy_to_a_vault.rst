:original_name: cbr_03_0029.html

.. _cbr_03_0029:

Applying a Policy to a Vault
============================

Scenarios
---------

You can apply a backup policy to a vault to run backup tasks at specified times or intervals. The generated backups can then be used to restore data quickly if data becomes corrupted or lost.

Constraints
-----------

-  You can create multiple policies, but you can only apply one backup policy to a vault.

Procedure
---------

#. Log in to the CBR console.

   a. In the upper left corner, click |image1| and select a region.
   b. Click |image2| and choose **Storage** > **Cloud Backup and Recovery**.

#. Locate the target vault and choose **More** > **Apply Backup Policy**.


   **Figure 1** Applying a backup policy

   |image3|

#. Select an existing backup policy from the drop-down list or create a new one. For how to create a policy, see :ref:`Creating a Backup Policy <cbr_03_0025>`.

#. After the policy is successfully applied, view details in the **Policies** area on the vault details page.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001599534545.jpg
.. |image3| image:: /_static/images/en-us_image_0000001232075371.png
