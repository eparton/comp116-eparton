Evan Parton (eparto01)
Oct 14, 2015
COMP 116 -- HW2 -- Incident Alarm

Correctly implemented for Live Stream are all scans: NULL scan, FIN scan, Xmas scan, Other Nmap scans, Nikto scan, and Credit Card leak. The Nikto scan I was not able to test directly since I was not able to get it working. I've a Mac and it was fighting with perl. I needed JSON-PP specifically for nikto. I got the JSON-PP module updated for perl, but this was not good enough.

Correctly implemented for the web server log is NMAP scan, Masscan, and phpMyAdmin. I did not get to the Nikto scan (explained above), the Shellshock, or anything like shellcode. I reviewed the Shellshock details however ran out of time before being able to understand exactly how the attack manifests itself in the log. With regards to the shellcode, I also ran out of time to do the particular regex needed here to identify executable code in the string.

I worked alone on this project, and discussed concepts and progress with Phil Braunstein. It took me approximately 15 hours.

I had never worked with Ruby before, which was a slight delay in getting started. Additionally I spent too long trying to understand PacketFu from the supplied materials, instead of reviewing and implementing actual functioning examples. Spending time with the examples was the necessary piece to bridge the theory with the practice.

1) The heuristics were mostly rudamentary, such as string searching and regex. This is a simple implementation that can be done in a few days. The searching logic doesn't involve complex comparisons to specific attacks, beyond the FIN, NULL, and XMAS. Using externally provided databases of known attacks we could search additional vectors beyond what we've hardcoded.

2) With more time, we could add advanced checks for repeated attempts at communicate with the server. I've implemented a 'memory' (of previous players) for the FIN scan, something similar can be performed on all scans. Also we could use established third party tools, such as Snort, which expands our ability to match with known attacks.
