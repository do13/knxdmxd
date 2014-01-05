---
layout: default
---

# What is knxdmxd

# Command line options

## -u &lt;address&gt;

Address of EIBD, defaults to local:/tmp/eib. You can use EIBD-IP connections with ip:&lt;IP-address&gt;.

## -c &lt;filename&gt;

Path and filename of configuration file. It is recommended to locate the knxdmxd.conf in /etc/knxdmxd.conf. If no option is given, the current directory is used (i.e. ./knxdmxd.conf).

## -p &lt;filename&gt;

Path and filename of PID file. It is recommended to locate the knxdmxd.pid in /var/run/knxdmxd.pid. If no option is given, the current directory is used (i.e. ./knxdmxd.pid).

## -d

Run as daemon

# Configuration

the configuration file conforms to JSON-standard. Malformed configuration files may cause the knxdmxd to crash. Strings have to encapuslated with quotation marks.

## channels

Channels are the basic building block of the configuration. They consist of at least have a name and DMX-address.

### &quot;name&quot; : &lt;string&gt;

Channel names are not restricted in length or composition. They must be unique within the configuration. It is recommended not to use umlauts.

### &quot;dmx&quot; : &lt;string&gt;

The DMX address has the notation &lt;universe&gt;.&lt;channel&gt;. According to standrad numbering, channel 0 and universe 0 do not exists. If the universe part is ommitted, universe 1 is assumed.

### &quot;statusga&quot; : &lt;string&gt;

If defined, a telegram with the current channel value will be send via EIBD to the specified address whenever a crossfade finishes.

### &quot;factor&quot; : &lt;float&lt;

Defaults to 1.0. All values set within knxdmxd for this channel are multiplied with this value. Can be used to adjust colors in RGB setups or for brightness corrections in multi-unit setups.

