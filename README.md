# PortNotAvailableWindowsFix
Fix for that nasty port not available error message

## Problem:
Typical error message:

"Ports are not available: exposing port TCP 0.0.0.0:<PORTNUMBER> -> 0.0.0.0:0: listen tcp 0.0.0.0:<PORTNUMBER>: bind: An attempt was made to access a socket in a way forbidden by its access permissions."

## Fix:

net stop winnat
netsh int ipv4 add excludedportrange protocol=tcp startport=<PORTNUMBER> numberofports=1
net start winnat

## Result:
Port can now be reserved :D
