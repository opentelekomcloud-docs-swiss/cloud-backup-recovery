:original_name: cbr_04_0001.html

.. _cbr_04_0001:

Before You Start
================

Overview
--------

Welcome to *Cloud Backup and Recovery API Reference*. Cloud Backup and Recovery (CBR) allows you to easily back up Elastic Cloud Servers (ECSs) and Elastic Volume Service (EVS) disks. If there is a virus attack, accidental deletion, or software or hardware fault, data can be restored to any point in the past when the data was backed up. With CBR, you can back up and restore data on the cloud.

You can use APIs provided in this document to perform operations on CBR, such as creating and deleting a vault, and creating a policy. For details about all supported operations, see :ref:`API Overview <cbr_04_0007>`.

Before calling CBR APIs, ensure that you have fully understood relevant concepts. For details, see section "Service Overview" in the *Cloud Backup and Recovery User Guide*.

API Calling
-----------

CBR supports Representational State Transfer (REST) APIs, allowing you to call APIs using HTTPS. For details about API calling, see :ref:`Making an API Request <cbr_04_0009>`.

Endpoints
---------

An endpoint is the **request address** for calling an API. Endpoints vary depending on services and regions. For the endpoints of CBR, see `Regions and Endpoints <https://docs.sc.otc.t-systems.com/en-us/endpoint/index.html>`__.

Constraints
-----------

The numbers of CBR resources that you can create are determined by your quota. To view or increase the quota, see section "Quotas" in the *Cloud Backup and Recovery User Guide*.

For more constraints, see the API description.

Concepts
--------

-  Domain

   A domain has full access permissions for all of its cloud services and resources. It can be used to reset user passwords and grant user permissions. The domain should not be used directly to perform routine management. For security purposes, create Identity and Access Management (IAM) users and grant them permissions for routine management.

-  User

   An IAM user is created by an account in IAM to use cloud services. Each IAM user has its own identity credentials (password and access keys).

   API authentication requires information such as the domain name, username, and password.

-  Region

   A region is a geographic area in which cloud resources are deployed. Availability zones (AZs) in the same region can communicate with each other over an intranet, while AZs in different regions are isolated from each other. Deploying cloud resources in different regions can better suit certain user requirements or comply with local laws or regulations.

-  AZ

   An AZ comprises of one or more physical data centers equipped with independent ventilation, fire, water, and electricity facilities. Computing, network, storage, and other resources in an AZ are logically divided into multiple clusters. AZs within a region are interconnected using high-speed optical fibers to allow you to build cross-AZ high-availability systems.

-  Project

   A project corresponds to a region. Default projects are defined to group and physically isolate resources (including computing, storage, and network resources) across regions. Users can be granted permissions in a default project to access all resources under their domains in the region associated with the project. If you need more refined access control, create subprojects under a default project and create resources in subprojects. Then you can assign users the permissions required to access only the resources in the specific subprojects.


   .. figure:: /_static/images/en-us_image_0000001924299688.png
      :alt: **Figure 1** Project isolation model

      **Figure 1** Project isolation model
