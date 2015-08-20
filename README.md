# -multi-host-munin-plugins
[Munin](https://github.com/munin-monitoring/munin) plugins for
[single node multi host graphs](http://demo.munin-monitoring.org/vpn/odroid.vpn/index.html#multihost).
These make use of [serafena](https://github.com/Bushmills/serafena).

There are two different versions of the same plugins.
The set in munin-node is executed from regular munin-node, as plugins.
You may want to use this version if the machine is running a munin node already,
of if you're planning to set it up as one.

The version in standalone is a bash written minimal munin node together with
all those plugins in a single file. This minimal node is invoked from xinetd,
the xinetd configuration file has been provided.
This version can be used to serve lanwide munin information through serafena,
without the need to install munin-node anywhere. A munin server is still required.
