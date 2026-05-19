# PORTSCANNING

The Fast-Lane Port Scanner 🚀
A port scanner is a network detective's first tool. It tells us what services a machine is
offering. Our goal was speed and accuracy.
How We Built It: The Need for Speed
To avoid spending hours waiting for a scan to complete, we leveraged multi-threading.
Instead of checking one port, waiting for the result, and moving to the next, our script
launches separate threads (worker processes) at once.
 Technology: We used Python's built-in socket library for the low-level network
connection logic.
 Method: The scanner performs a TCP Connect Scan, which attempts a full, three-way
handshake. If the connection completes, the port is marked as OPEN.
 Key Function: The connect_ex() function is crucial—it's designed to return an error
code (0 for success) instead of crashing the program on a closed port.
Code Snippet (Focus on the 'Engine')
The use of threading.Thread and the Queue module ensures that our 50 workers efficiently
pull the next port number to check without stepping on each other's toes.
