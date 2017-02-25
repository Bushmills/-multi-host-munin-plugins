# -multi-host-munin-plugins
[Munin](https://github.com/munin-monitoring/munin) plugins for
[single node multi host graphs](http://demo.munin-monitoring.org/vpn/multihost.vpn).
These make use of [serafena](https://github.com/Bushmills/serafena), by signalling to receiving hosts execution of
[service status](https://github.com/Bushmills/serafena/blob/master/signal.handler/service_status). Receiving hosts are gathered in a group by the name "munin", so they can all be addressed in a single command: signal @munin status.
As the output has been parse-friendlyly formatted, the netwide plugin becomes rather simple.

An example of produced output is shown [here](http://demo.munin-monitoring.org/vpn/vpn/)

There are two different versions of the same plugins.
The set in [munin-node](https://github.com/Bushmills/-multi-host-munin-plugins/tree/master/munin-node)
is executed from regular munin-node, as plugins. You may want to use this 
version if the machine is running as munin node already, of if you're planning
to set it up as one.

The version in [standalone](https://github.com/Bushmills/-multi-host-munin-plugins/tree/master/standalone) is a bash written minimal munin node together with
all those plugins in a single file. This minimal node is invoked from xinetd,
the xinetd configuration file has been provided.

Either version serves lanwide munin information, which is collected by sending
request to the hosts through through [serafena](https://github.com/Bushmills/serafena),
Hosts reply to requests to service "status". None of the hosts need to be regular
munin nodes, when using standalone version. For the plugin set for regular
munin node, only the host running the plugins needs to be a regular munin node.

