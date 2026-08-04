:original_name: cbr_03_0010.html

.. _cbr_03_0010:

Managing Vault Tags
===================

Scenarios
---------

For existing vaults, you can add, edit, or delete tags as needed. Tags are used only for filtering and managing vaults.

Procedure
---------

#. Log in to the CBR console.

   a. In the upper left corner, click |image1| and select a region.
   b. Click |image2| and choose **Storage** > **Cloud Backup and Recovery**.

#. On the **Vaults** tab, click the name of the target vault and then select the **Tags** tab.

   -  Adding a tag

      a. Click **Edit Tag** in the upper left corner.

      b. In the dialog box on the right, click **Add**. Then, enter a tag key and tag value.

         Tags are key-value pairs, which are used to identify, classify, and search for vaults. You can add a maximum of 20 tags for a vault, and vault tags are only used to filter and manage vaults. See :ref:`Figure 1 <cbr_03_0010__fig19773171091318>`.

         .. _cbr_03_0010__fig19773171091318:

         .. figure:: /_static/images/en-us_image_0000002021475630.png
            :alt: **Figure 1** Adding a tag

            **Figure 1** Adding a tag

         :ref:`Table 1 <cbr_03_0010__table103661428132915>` describes the parameters of a tag.

         .. _cbr_03_0010__table103661428132915:

         .. table:: **Table 1** Tag parameter description

            +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
            | Parameter             | Description                                                                                                                           | Example Value         |
            +=======================+=======================================================================================================================================+=======================+
            | Key                   | Tag key. Each tag of a vault has a unique key. The tag key is mandatory and has no default value. You can enter a custom key.         | Key_0001              |
            |                       |                                                                                                                                       |                       |
            |                       | A tag key:                                                                                                                            |                       |
            |                       |                                                                                                                                       |                       |
            |                       | -  Can contain 1 to 36 Unicode characters.                                                                                            |                       |
            |                       | -  Can contain only letters, digits, hyphens (-), and underscores (_).                                                                |                       |
            +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
            | Value                 | Tag value. Different tag keys can share the same value. Tag values are optional and can be left blank. There is no default tag value. | Value_0001            |
            |                       |                                                                                                                                       |                       |
            |                       | A tag value:                                                                                                                          |                       |
            |                       |                                                                                                                                       |                       |
            |                       | -  Can contain 0 to 43 Unicode characters.                                                                                            |                       |
            |                       | -  Can contain only letters, digits, hyphens (-), and underscores (_).                                                                |                       |
            +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

      c. Click **OK**. After the tag is added, it is displayed in the tag list.

   -  Editing a tag

      a. Click **Edit Tag** in the upper left corner.
      b. In the dialog box on the right, change the tag key or value. For details about these parameters, see :ref:`Table 1 <cbr_03_0010__table103661428132915>`.
      c. Click **OK**. After the tag is edited, you can view the tag in the tag list.

   -  Deleting a tag

      a. Click **Edit Tag** in the upper left corner.
      b. In the dialog box on the right, click **Delete** next to the tag you want to delete.
      c. Click **OK**. After the tag is deleted, the tag is not displayed in the tag list anymore.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001599534545.jpg
