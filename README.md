# RULES AND USAGE MODE
# -Add a file named "ADDRESSING" in each exercise directory, in which the networks/subnetworks addresses are written, e.g.:
#   NETWORK: 192.168.0.0/24
#   LAN1: 192.168.0.0/25
#   LAN2: 192.168.0.128/25
# -Add a bash script "ping" in each exercise directory's shared folder, in which the ping commands (set the flag "-c 1" for readability) for every host and for an external website (e.g., www.google.it) are written, e.g.:
#   #!/bin/bash
#   ping 192.168.0.1 -c 1
#   ping 192.168.0.2 -c 1
#   ...
#   ping www.google.it -c 1
