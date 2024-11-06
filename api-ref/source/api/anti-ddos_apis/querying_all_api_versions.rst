:original_name: antiddos_02_0002.html

.. _antiddos_02_0002:

Querying All API Versions
=========================

Functions
---------

This API allows you to query all API versions.

URI
---

-  URI format

   GET /

Request
-------

**Request parameters**

None

Response Messages
-----------------

-  Parameter description

   +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------+
   | Name                  | Type                  | Description                                                                                                                                        |
   +=======================+=======================+====================================================================================================================================================+
   | versions              | List data structure   | API versions                                                                                                                                       |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------+
   | id                    | String                | Version ID (Version number), for example, v 1                                                                                                      |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------+
   | links                 | List data structure   | URLs of the APIs                                                                                                                                   |
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

   ========= ====== ============
   Parameter Type   Description
   ========= ====== ============
   href      String URLs of APIs
   rel       String self
   ========= ====== ============

Example
-------

-  Example request

   .. code-block:: text

      GET /

-  Example response

   .. code-block::

      {
        "versions": [
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
          },
          {
            "id": "v2",
            "links": [
              {
                "href": "https://antiddos.eu-de.otc.t-systems.com/v2/",
                "rel": "self"
              }
            ],
            "min_version": "",
            "status": "CURRENT",
            "updated": "2018-09-18T00:00:00Z",
            "version": ""
          }
        ]
      }

Status Code
-----------

For details, see :ref:`Status Code <antiddos_02_0031>`.
