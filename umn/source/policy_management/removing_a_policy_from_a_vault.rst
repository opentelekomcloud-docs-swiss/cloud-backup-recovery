:original_name: cbr_03_0030.html

.. _cbr_03_0030:

Removing a Policy from a Vault
==============================

If you no longer need automatic backup for a vault, remove the policy from the vault.

Prerequisites
-------------

A policy has been applied to the vault.

Procedure
---------

#. Log in to the CBR console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select a region.
   c. Click |image2| and choose **Storage** > **Cloud Backup and Recovery**. Select a backup type from the left navigation pane.

#. Find the target vault and click the vault name to view its details.

#. In the **Policies** area, click **Remove Policy**. See :ref:`Figure 1 <cbr_03_0030__fig16691161117510>`.

   .. _cbr_03_0030__fig16691161117510:

   **Figure 1** Removing a policy

   |image3|

   .. note::

      -  If a policy is removed when a backup task is being executed for a resource in the vault, the backup task will continue and backups will be generated.
      -  After a policy is removed, backups retained by **Time period** will expire based on the retention rule, but backups retained by **Backup quantity** will not. You need manually delete unwanted backups.

#. Click **Yes**.

   Tasks will no longer be executed based on this policy for the vault.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001599534545.jpg
.. |image3| image:: /_static/images/en-us_image_0184119988.png
