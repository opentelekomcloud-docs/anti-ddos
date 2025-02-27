:original_name: antiddos_02_0023.html

.. _antiddos_02_0023:

Querying the List of EIP Defense Statuses
=========================================

Functions
---------

This API enables you to query the defense statuses of all EIPs, regardless whether an EIP has been bound to an Elastic Cloud Server (ECS) or not.

URI
---

-  URI format

   GET /v1/{project_id}/antiddos

   .. note::

      You can use **?** and **&** behind the URI to add query conditions, as shown in the request example.

-  Parameter description

   ========== ========= ====== ===========
   Parameter  Mandatory Type   Description
   ========== ========= ====== ===========
   project_id Yes       String User ID
   ========== ========= ====== ===========

Request
-------

.. table:: **Table 1** Parameter description

   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                                                                                |
   +=================+=================+=================+============================================================================================================================================================================================+
   | status          | No              | String          | Possible values:                                                                                                                                                                           |
   |                 |                 |                 |                                                                                                                                                                                            |
   |                 |                 |                 | -  **normal**: indicates that the defense status is normal.                                                                                                                                |
   |                 |                 |                 | -  **configuring**: indicates that defense is being configured.                                                                                                                            |
   |                 |                 |                 | -  **notConfig**: indicates that defense is not configured.                                                                                                                                |
   |                 |                 |                 | -  **packetcleaning**: indicates that traffic cleaning is underway.                                                                                                                        |
   |                 |                 |                 | -  **packetdropping**: indicates that traffic is discarded.                                                                                                                                |
   |                 |                 |                 |                                                                                                                                                                                            |
   |                 |                 |                 | If this parameter is not used, the defense statuses of all ECSs are displayed in the Neutron-queried order by default.                                                                     |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | limit           | No              | Integer         | Maximum number of returned results. The value ranges from 1 to 100.                                                                                                                        |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | offset          | No              | Integer         | Offset. The value ranges from 0 to 2147483647.                                                                                                                                             |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | ip              | No              | String          | IP address. Both IPv4 and IPv6 addresses are supported. For example, if you enter **?ip=192.168**, the defense status of EIPs corresponding to 192.168.111.1 and 10.192.168.8 is returned. |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Response
--------

-  Parameter description

   ========== =================== ========================
   Name       Type                Description
   ========== =================== ========================
   total      Integer             Total number of EIPs
   ddosStatus List data structure List of defense statuses
   ========== =================== ========================

-  Data structure description of **ddosStatus**

   +-----------------------+-----------------------+---------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                           |
   +=======================+=======================+=======================================================================================+
   | floating_ip_address   | String                | Floating IP address                                                                   |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------+
   | floating_ip_id        | String                | ID of an EIP                                                                          |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------+
   | network_type          | String                | EIP type. The value can be:                                                           |
   |                       |                       |                                                                                       |
   |                       |                       | -  **EIP**: EIP that is bound or not bound with ECS.                                  |
   |                       |                       | -  **ELB**: EIP that is bound with ELB.                                               |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------+
   | status                | String                | Defense status, the possible value of which is one of the following:                  |
   |                       |                       |                                                                                       |
   |                       |                       | -  **normal**: indicates that the defense status is normal.                           |
   |                       |                       | -  **configuring**: indicates that defense is being configured.                       |
   |                       |                       | -  **notConfig**: indicates that defense is not configured.                           |
   |                       |                       | -  **packetcleaning**: indicates that traffic cleaning is underway.                   |
   |                       |                       | -  **packetdropping**: indicates that traffic is discarded.                           |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------+
   | blackhole_endtime     | Long                  | End time of a black hole                                                              |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------+
   | protect_type          | String                | Protection type                                                                       |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------+
   | traffic_threshold     | Long                  | Traffic threshold                                                                     |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------+
   | http_threshold        | Long                  | HTTP traffic threshold                                                                |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------+
   | traffic_pos_id        | Long                  | Traffic triggering parameter                                                          |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------+
   | protect_capacity      | Long                  | Protection capacity. The value **0** indicates that protection is not supported.      |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------+
   | current_usage         | Long                  | Used protection capacity. The value **0** indicates that protection is not supported. |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------+
   | enterprise_project_id | String                | Enterprise project ID                                                                 |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------+

Example
-------

-  Example request

   .. code-block:: text

      GET /v1/67641fe6886f43fcb78edbbf0ad0b99f/antiddos?status=packetdropping

-  Example response

   .. code-block::

      {
         "total": 5,
         "ddosStatus": [
            {
               "floating_ip_id": "1867f954-fc11-4202-8247-6af2144867ea",
               "floating_ip_address": "192.168.42.221",
               "network_type": "EIP",
               "status": "notConfig"
            },
            {
               "floating_ip_id": "49c6af49-9ace-42e6-ab89-1eee1f4ac821",
               "floating_ip_address": "192.168.35.152",
               "network_type": "EIP",
               "status": "normal"
            },
            {
               "floating_ip_id": "7a8dc957-083b-499d-b7cf-6fa48f4880c5",
               "floating_ip_address": "192.168.42.222",
               "network_type": "EIP",
               "status": "notConfig"
            },
            {
               "floating_ip_id": "7c6676a0-b281-4163-9d0d-cb6485ae9860",
               "floating_ip_address": "192.168.44.69",
               "network_type": "EIP",
               "status": "normal"
            },
            {
               "floating_ip_id": "969c1d48-6a92-4ef1-b66c-b17c7e7d7ce7",
               "floating_ip_address": "192.168.47.192",
               "network_type": "EIP",
               "status": "notConfig"
            }
         ]
      }

Status Code
-----------

See :ref:`Status Code <antiddos_02_0031>`.
