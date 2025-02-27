:original_name: antiddos_02_0038.html

.. _antiddos_02_0038:

Configuring the Default Protection Policy for Newly Purchased Public IP Addresses
=================================================================================

Functions
---------

This API enables you to configure the default protection policy. After a protection policy is configured, it applies to the newly purchased public IP addresses.

URI
---

-  URI format

   POST /v1/{project_id}/antiddos/default-config

-  Parameter description

   ========== ========= ====== ===========
   Parameter  Mandatory Type   Description
   ========== ========= ====== ===========
   project_id Yes       String User ID
   ========== ========= ====== ===========

Request
-------

.. table:: **Table 1** Parameter description

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

.. note::

   If values of **traffic_pos_id**, **http_request_pos_id**, **cleaning_access_pos_id** are set between **33 to 36**, their values must be the same.

Response
--------

-  Parameter description

   ========== ====== ==========================
   Name       Type   Description
   ========== ====== ==========================
   statusCode String Internal error code
   body       String Internal error description
   header     String Internal error code header
   ========== ====== ==========================

Example
-------

-  Example request

   .. code-block:: text

      POST /v1/67641fe6886f43fcb78edbbf0ad0b99f/antiddos/default-config

   .. code-block::

      {
          "enable_L7":true,
          "traffic_pos_id":1,
          "http_request_pos_id":1,
          "cleaning_access_pos_id":1,
          "app_type_id":1
      }

-  Example response

   .. code-block::

      {
          "statusCode": 0,
          "body": null,
          "header": null
      }

Status Code
-----------

For details, see :ref:`Status Code <antiddos_02_0031>`.
