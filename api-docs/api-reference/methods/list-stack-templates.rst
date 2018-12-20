
.. _list-stack-template:

List base templates
~~~~~~~~~~~~~~~~~

.. code::

    GET /v1/{tenant_id}/templates

List base templates on account

This table shows the possible response codes for this operation:

+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |Success                  |Request succeeded.       |
+--------------------------+-------------------------+-------------------------+


Request
-------

This table shows the URI parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|{tenant_id}               |String                   |The ID of the tenant. A  |
|                          |                         |tenant is also known as  |
|                          |                         |an account or project.   |
+--------------------------+-------------------------+-------------------------+


Response
--------



**Example List base templates: JSON response**

This response has been shortened.

.. code::

   {
       "Description": "A template that provides a single server instance.",
       "Parameters": {
           "server-size": {
               "default": "1GB Standard Instance",
               "description": "Server size",
               "type": "String",
               "constraints": [
                   {
                       "allowed_values": [
                           "512MB Standard Instance",
                           "1GB Standard Instance",
                           "4GB Standard Instance",
                           "8GB Standard Instance"
                       ],
                       "description": "Must be a valid server size."
                   }
               ]
           },
           "key_name": {
               "description": "Keypair name for SSH access to the server",
               "required": true,
               "type": "String"
           },
           "server_name": {
               "default": "My server",
               "description": "My server",
               "type": "String"
           }
       },
       "ParameterGroups": [
           {
               "label": "Parameter groups",
               "description": "My parameter groups",
               "parameters": [
                   "param_name-1",
                   "param_name-2"
               ]
           }
       ]
   }
