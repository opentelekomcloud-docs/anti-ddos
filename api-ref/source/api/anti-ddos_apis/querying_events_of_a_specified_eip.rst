:original_name: antiddos_02_0026.html

.. _antiddos_02_0026:

Querying Events of a Specified EIP
==================================

Functions
---------

This API allows you to query events of a specified EIP in the last 24 hours. Events include cleaning and blackhole events, and the query delay is within five minutes.

URI
---

-  URI format

   GET /v1/{project_id}/antiddos/{floating_ip_id}/logs

   .. note::

      You can use **?** and **&** behind the URI to add query conditions, as shown in the request example.

-  Parameter description

   ============== ========= ====== =====================================
   Parameter      Mandatory Type   Description
   ============== ========= ====== =====================================
   project_id     Yes       String User ID
   floating_ip_id Yes       String ID corresponding to the EIP of a user
   ============== ========= ====== =====================================

Request
-------

.. table:: **Table 1** Parameter description

   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                                                                                  |
   +=================+=================+=================+==============================================================================================================================================================================================+
   | limit           | No              | Integer         | Limit of number of returned results or the maximum number of returned results of a query. The value ranges from 1 to 100, and this parameter is used together with the **offset** parameter. |
   |                 |                 |                 |                                                                                                                                                                                              |
   |                 |                 |                 | If neither **limit** nor **offset** is used, query results of all ECSs are returned.                                                                                                         |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | offset          | No              | Integer         | Offset. This parameter is valid only when used together with the **limit** parameter.                                                                                                        |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | sort_dir        | No              | String          | Possible values:                                                                                                                                                                             |
   |                 |                 |                 |                                                                                                                                                                                              |
   |                 |                 |                 | -  **desc**: indicates that query results are given and sorted by time in descending order.                                                                                                  |
   |                 |                 |                 | -  **asc**: indicates that query results are given and sorted by time in ascending order.                                                                                                    |
   |                 |                 |                 |                                                                                                                                                                                              |
   |                 |                 |                 | The default value is **desc**.                                                                                                                                                               |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Response
--------

-  Parameter description

   ===== ============== ====================
   Name  Type           Description
   ===== ============== ====================
   total Integer        Total number of EIPs
   logs  Data structure List of events
   ===== ============== ====================

-  Data structure description of **logs**

   +-----------------------+-----------------------+----------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                          |
   +=======================+=======================+======================================================================+
   | start_time            | Long integer          | Start time                                                           |
   +-----------------------+-----------------------+----------------------------------------------------------------------+
   | end_time              | Long integer          | End time                                                             |
   +-----------------------+-----------------------+----------------------------------------------------------------------+
   | status                | Integer               | Defense status, the possible value of which is one of the following: |
   |                       |                       |                                                                      |
   |                       |                       | -  **1**: indicates that traffic cleaning is underway.               |
   |                       |                       | -  **2**: indicates that traffic is discarded.                       |
   +-----------------------+-----------------------+----------------------------------------------------------------------+
   | trigger_bps           | Integer               | Traffic at the triggering point                                      |
   +-----------------------+-----------------------+----------------------------------------------------------------------+
   | trigger_pps           | Integer               | Packet rate at the triggering point                                  |
   +-----------------------+-----------------------+----------------------------------------------------------------------+
   | trigger_http_pps      | Integer               | HTTP request rate at the triggering point                            |
   +-----------------------+-----------------------+----------------------------------------------------------------------+

Example
-------

-  Example request

   .. code-block:: text

      GET /v1/67641fe6886f43fcb78edbbf0ad0b99f/antiddos/1df977c2-fdc6-4483-bc1c-ba46829f57b8/logs

-  Example response

   .. code-block::

      {
         "total": 1,
         "logs": [
            {
               "start_time": 1473217200000,
               "end_time": 1473242400000,
               "status": 1,
               "trigger_bps": 51106,
               "trigger_pps": 2600,
               "trigger_http_pps": 3589
            }
         ]
      }

Status Code
-----------

See :ref:`Status Code <antiddos_02_0031>`.
