:original_name: antiddos_02_0020.html

.. _antiddos_02_0020:

Querying Configured Anti-DDoS Defense Policies
==============================================

Functions
---------

This API enables you to query the Anti-DDoS defense policy of a specified EIP.

URI
---

-  URI format

   GET /v1/{project_id}/antiddos/{floating_ip_id}

-  Parameter description

   ============== ========= ====== =====================================
   Parameter      Mandatory Type   Description
   ============== ========= ====== =====================================
   project_id     Yes       String User ID
   floating_ip_id Yes       String ID corresponding to the EIP of a user
   ============== ========= ====== =====================================

Request
-------

**Request parameters**

None

Response
--------

.. table:: **Table 1** Parameter description

   +------------------------+-----------------------+------------------------------------------------------------------------------------------------+
   | Parameter              | Type                  | Description                                                                                    |
   +========================+=======================+================================================================================================+
   | enable_L7              | Boolean               | Whether L7 defense has been enabled.                                                           |
   +------------------------+-----------------------+------------------------------------------------------------------------------------------------+
   | traffic_pos_id         | Integer               | Position ID of traffic. The value ranges from 1 to 9, or 99, or 33 to 36.                      |
   +------------------------+-----------------------+------------------------------------------------------------------------------------------------+
   | http_request_pos_id    | Integer               | Position ID of number of HTTP requests. The value ranges from 1 to 15 and 33 to 36.            |
   +------------------------+-----------------------+------------------------------------------------------------------------------------------------+
   | cleaning_access_pos_id | Integer               | Position ID of access limit during cleaning. The value ranges from 1 to 8, or 99, or 33 to 36. |
   +------------------------+-----------------------+------------------------------------------------------------------------------------------------+
   | app_type_id            | Integer               | Application type ID. Possible values:                                                          |
   |                        |                       |                                                                                                |
   |                        |                       | -  0                                                                                           |
   |                        |                       | -  1                                                                                           |
   +------------------------+-----------------------+------------------------------------------------------------------------------------------------+

Example
-------

-  Example request

   .. code-block:: text

      GET /v1/67641fe6886f43fcb78edbbf0ad0b99f/antiddos/1df977c2-fdc6-4483-bc1c-ba46829f57b8

-  Example response

   .. code-block::

      {
         "enable_L7": true,
         "traffic_pos_id": 1,
         "http_request_pos_id": 1,
         "cleaning_access_pos_id": 1,
         "app_type_id": 1
      }

Status Code
-----------

See :ref:`Status Code <antiddos_02_0031>`.
