:original_name: antiddos_02_0019.html

.. _antiddos_02_0019:

Disabling Anti-DDoS
===================

Functions
---------

This asynchronous API allows you to disable the Anti-DDoS traffic scrubbing. Successfully invoking this API only means that the service node has received the disabling request. You need to use the task querying API to check the task execution status. For details about the task querying API, see :ref:`Querying Anti-DDoS Tasks <antiddos_02_0022>`.

URI
---

-  URI format

   DELETE /v1/{project_id}/antiddos/{floating_ip_id}

-  Parameter description

   ============== ========= ====== =====================================
   Parameter      Mandatory Type   Description
   ============== ========= ====== =====================================
   project_id     Yes       String User ID
   floating_ip_id Yes       String ID corresponding to the EIP of a user
   ============== ========= ====== =====================================

Request
-------

None

Response
--------

.. table:: **Table 1** Parameter description

   +-----------------------+-----------------------+----------------------------------------------------------------------------------+
   | Name                  | Type                  | Description                                                                      |
   +=======================+=======================+==================================================================================+
   | error_code            | String                | Internal error code                                                              |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------+
   | error_description     | String                | Internal error description                                                       |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------+
   | task_id               | String                | ID of a task. This ID can be used to query the status of the task.               |
   |                       |                       |                                                                                  |
   |                       |                       | This field is reserved for use in task auditing later. It is temporarily unused. |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------+

Example
-------

-  Example request

   .. code-block:: text

      DELETE /v1/67641fe6886f43fcb78edbbf0ad0b99f/antiddos/1df977c2-fdc6-4483-bc1c-ba46829f57b8

-  Example response

   .. code-block::

      {
         "error_code": "10000000",
         "error_description": "Task has been received and is being processed.",
         "task_id": "d90dc577-abd2-4be0-b2cf-cb8f5f67ddb0"
      }

Status Code
-----------

See :ref:`Status Code <antiddos_02_0031>`.
