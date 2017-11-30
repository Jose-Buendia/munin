Role Name
=========

Install a munin-master server

Requirements
------------

Ubuntu 14.04

Role Variables
--------------

# monitored munin nodes
munin_hosts:
  - {
    name: "localhost",
    address: "127.0.0.1",
    extra: ["use_node_name yes"]
  }
# Will be translated into:
# [host]
#   address: [name]
#   [extra.0]
#   [extra.1]
#   [...]
#
# Note that `name` can be hostname, or group + hostname, for example:
# [example.com;foo.example.com]

# munin contacts
munin_contacts: []
#  - {
#    name: "JohnDoe",
#    email: "johndoe@example.com",
#    subject: "Munin-notification for ${var:group} :: ${var:host}",
#    level: "warning critical"
#   }


# list of contacts name sperated by space which receive all alerts
munin_default_contacts: "no"

Dependencies
------------

None

License
-------

BSD

Author Information
------------------

STEAMULO - http://www.steamulo.com
