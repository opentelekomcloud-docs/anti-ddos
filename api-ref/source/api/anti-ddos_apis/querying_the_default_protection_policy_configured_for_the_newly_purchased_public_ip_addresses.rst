:original_name: antiddos_02_0037.html

.. _antiddos_02_0037:

Querying the Default Protection Policy Configured for the Newly Purchased Public IP Addresses
=============================================================================================

Functions
---------

This API enables you to query the default protection policy configured for the newly purchased public IP addresses.

URI
---

-  URI format

   GET /v1/{project_id}/antiddos/default-config

-  Parameter description

   ========== ========= ====== ===========
   Parameter  Mandatory Type   Description
   ========== ========= ====== ===========
   project_id Yes       String User ID
   ========== ========= ====== ===========

Request
-------

**Request parameters**

None

Response
--------

-  Parameter description

   +------------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------+
   | Parameter              | Mandatory       | Type            | Description                                                                                    |
   +========================+=================+=================+================================================================================================+
   | enable_L7              | Yes             | Boolean         | Whether to enable layer-7 protection.                                                          |
   +------------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------+
   | traffic_pos_id         | Yes             | Integer         | Position ID of traffic. The value ranges from 1 to 9, or 99, or 33 to 36.                      |
   +------------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------+
   | http_request_pos_id    | Yes             | Integer         | Position ID of number of HTTP requests. The value ranges from 1 to 15 and 33 to 36.            |
   +------------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------+
   | cleaning_access_pos_id | Yes             | Integer         | Position ID of access limit during cleaning. The value ranges from 1 to 8, or 99, or 33 to 36. |
   +------------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------+
   | app_type_id            | Yes             | Integer         | Application type ID. Possible values:                                                          |
   |                        |                 |                 |                                                                                                |
   |                        |                 |                 | -  0                                                                                           |
   |                        |                 |                 | -  1                                                                                           |
   +------------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------+

Example
-------

-  Example request

   .. code-block:: text

      GET /v1/67641fe6886f43fcb78edbbf0ad0b99f/antiddos/default/config

-  Example response

   .. code-block::

      {
          "enable_L7":true,
          "traffic_pos_id":1,
          "http_request_pos_id":1,
          "cleaning_access_pos_id":1,
          "app_type_id":1
      }

Status Code
-----------

For details, see :ref:`Status Code <antiddos_02_0031>`.
