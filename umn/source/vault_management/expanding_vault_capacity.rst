:original_name: cbr_03_0006.html

.. _cbr_03_0006:

Expanding Vault Capacity
========================

You can expand the size of a vault if its total capacity is insufficient.

Procedure
---------

#. Log in to the CBR console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select a region.
   c. Click |image2| and choose **Storage** > **Cloud Backup and Recovery**. Select a backup type from the left navigation pane.

#. Find the target vault and choose **More** > **Expand Capacity** in the **Operation** column. See :ref:`Figure 1 <cbr_03_0006__fig624235516355>`.

   .. _cbr_03_0006__fig624235516355:

   **Figure 1** Expanding vault capacity

   |image3|

#. Enter the capacity to be added. The minimum value is **1**.

#. Click **Next**. Confirm the settings and click **Submit**.

#. Return to the vault list and check that the capacity of the vault has been expanded.

Auto Capacity Expansion
-----------------------

If you want a vault to be automatically expanded when its capacity is used up, enable auto capacity expansion.

If this function is enabled, the vault capacity will be automatically expanded to 1.25 times its current capacity when its capacity is used up.

#. Log in to the CBR console.

   a. Log in to the management console.
   b. Click |image4| in the upper left corner and select a region.
   c. Click |image5| and choose **Storage** > **Cloud Backup and Recovery**. Select a backup type from the left navigation pane.

#. Find the target vault and click its name.

#. On the vault details page, enable **Auto Capacity Expansion**.

   |image6|

   If **Auto Capacity Expansion** is turned on, the function is enabled.

#. (Optional) Disable **Auto Capacity Expansion** if you no longer need this function.

   If **Auto Capacity Expansion** is turned off, the function is disabled.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001599534545.jpg
.. |image3| image:: /_static/images/en-us_image_0000002021314946.png
.. |image4| image:: /_static/images/en-us_image_0159365094.png
.. |image5| image:: /_static/images/en-us_image_0000001599534545.jpg
.. |image6| image:: /_static/images/en-us_image_0000002329072249.png
