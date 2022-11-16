:original_name: antiddos_02_0007.html

.. _antiddos_02_0007:

Querying a Specified API Version
================================

Functions
---------

This API allows you to query a specified API version.

URI
---

-  URI format

   GET /{version_id}

Request
-------

**Request parameters**

None

Response
--------

-  Parameter description

   +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------+
   | Name                  | Type                  | Description                                                                                                                                        |
   +=======================+=======================+====================================================================================================================================================+
   | version               | Data structure        | Version object                                                                                                                                     |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------+
   | id                    | String                | Version ID (Version number), for example, v 1                                                                                                      |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------+
   | links                 | List data structure   | URL of the API                                                                                                                                     |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------+
   | min_version           | String                | If this API version supports microversions, the minimum microversion number is returned. If microversions are not supported, no value is returned. |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------+
   | status                | String                | Version status. Valid values are as follows:                                                                                                       |
   |                       |                       |                                                                                                                                                    |
   |                       |                       | CURRENT: Indicates that the version is the primary version.                                                                                        |
   |                       |                       |                                                                                                                                                    |
   |                       |                       | SUPPORTED: Indicates that the version is an old version, but it is still supported.                                                                |
   |                       |                       |                                                                                                                                                    |
   |                       |                       | DEPRECATED: Indicates that this version is a discarded version and may be deleted later.                                                           |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------+
   | updated               | String                | Version release time                                                                                                                               |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------+
   | version               | String                | If this API version supports microversions, the maximum microversion number is returned. If microversions are not supported, no value is returned. |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------+

-  Data structure description of **links**

   ========= ========= ====== ==============
   Parameter Mandatory Type   Description
   ========= ========= ====== ==============
   href      Yes       String URL of the API
   rel       Yes       String self
   ========= ========= ====== ==============

Example
-------

-  Example request

   .. code-block:: text

      GET /v1

-  Example response

   .. code-block::

      {
        "version":
         {
            "id": "v1",
            "links": [
              {
                "href": "https://antiddos.eu-de.otc.t-systems.com/v1/",
                "rel": "self"
              }
            ],
            "min_version": "",
            "status": "CURRENT",
            "updated": "2016-10-29T00:00:00Z",
            "version": ""
         }
      }

Status Code
-----------

For details, see :ref:`Status Code <antiddos_02_0031>`.
