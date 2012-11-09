mdadm_notify
========

Bash script used by mdadm on Linux to send notifications of RAID events to the sys admin

Usage
-----
Simply edit your mdadm.conf to reference this script for the PROGRAM parameter:
<pre>
# mdadm configuration file
#
# mdadm will function properly without the use of a configuration file,
# but this file is useful for keeping track of arrays and member disks.
# In general, a mdadm.conf file is created, and updated, after arrays
# are created. This is the opposite behavior of /etc/raidtab which is
# created prior to array construction.
#
# When used in --follow (aka --monitor) mode, mdadm needs a
# mail address and/or a program.  This can be given with "mailaddr"
# and "program" lines to that monitoring can be started using
#    mdadm --follow --scan & echo $! > /var/run/mdadm
# If the lines are not found, mdadm will exit quietly
#
PROGRAM /root/bin/mdadm_notify
#
ARRAY /dev/md0 level=raid5 metadata=1.2 num-devices=3 UUID=70a588b7:5f7ad965:cd7d2a21:12db71ed
</pre>

Requirements
------------
GNU Bash

Example Output
--------------
<pre>
/dev/md0 has DISAPPEARED
</pre>

Bugs
----
Find a bug? Please create an issue here on GitHub at:
https://github.com/hunleyd/mdadm_notify/issues

Twitter
-------
Keep up to date on announcements and more by following Doug on Twitter, <a href="http://twitter.com/hunleyd">@hunleyd</a>

Authors
-------
**Douglas J Hunley**
+ G+: http://goo.gl/sajR3
+ Twitter: http://twitter.com/hunleyd
+ GitHub: http://github.com/hunleyd

Copyright and license
---------------------
Copyright 2012 Douglas J Hunley.

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this work
except in compliance with the License. You may obtain a copy of the License in the
LICENSE file, or at:

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the
License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND,
either express or implied. See the License for the specific language governing
permissions and limitations under the License.
