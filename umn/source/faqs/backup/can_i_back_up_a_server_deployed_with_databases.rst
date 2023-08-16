:original_name: cbr_06_0008.html

.. _cbr_06_0008:

Can I Back Up a Server Deployed with Databases?
===============================================

Yes. To back up applications requiring strict consistency, such as databases and email systems, you are advised to suspend all write operations and then perform backup. If write operations cannot be suspended, you can stop the application systems or the server for offline backup. Without doing these, status of the server after restoration is similar to restart upon an unexpected power failure and log rollback will be performed on databases to keep data consistent.
