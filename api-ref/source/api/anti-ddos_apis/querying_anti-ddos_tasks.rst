:original_name: antiddos_02_0022.html

.. _antiddos_02_0022:

Querying Anti-DDoS Tasks
========================

Functions
---------

This API enables you to query the execution status of a specified Anti-DDoS configuration task.

URI
---

-  URI format

   GET /v1/{project_id}/query_task_status

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

   +-----------+-----------+--------+------------------------------------------------+
   | Parameter | Mandatory | Type   | Description                                    |
   +===========+===========+========+================================================+
   | task_id   | Yes       | String | Task ID (nonnegative integer) character string |
   +-----------+-----------+--------+------------------------------------------------+

Response
--------

-  Parameter description

   +-----------------------+-----------------------+------------------------------------------------------+
   | Name                  | Type                  | Description                                          |
   +=======================+=======================+======================================================+
   | task_status           | String                | Status of a task, which can be one of the following: |
   |                       |                       |                                                      |
   |                       |                       | -  success                                           |
   |                       |                       | -  failed                                            |
   |                       |                       | -  waiting                                           |
   |                       |                       | -  running                                           |
   |                       |                       | -  preprocess                                        |
   |                       |                       | -  ready                                             |
   +-----------------------+-----------------------+------------------------------------------------------+
   | task_msg              | String                | Additional information about a task                  |
   +-----------------------+-----------------------+------------------------------------------------------+

Example
-------

-  Example request

   .. code-block:: text

      GET /v1/67641fe6886f43fcb78edbbf0ad0b99f/query_task_status?task_id=4a4fefe7-34a1-40e2-a87c-16932af3ac4a

-  Example response

   .. code-block::

      {
         "task_status": "running",
         "task_msg": ""
      }

Status Code
-----------

See :ref:`Status Code <antiddos_02_0031>`.
