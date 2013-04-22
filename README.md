# HTTPING PLUGIN FOR MUNIN

## Installation

``` shell
cd /usr/share/munin/plugins/
wget --no-check-certificate https://raw.github.com/zembutsu/munin-plugin-httping_/master/httping_
chmod +x httping_
ln -s /usr/share/munin/plugins/httping_ /etc/munin/plugins/httping_localhost
```

`/etc/munin/plugin-conf.d/munin-node`, add at the bottom

```
[httping_localhost]
    env.URL	http://localhost/
    env.COUNT	5
    env.connect_warning 0.400
    env.connect_critical 0.700
    env.processing_warning 0.400
    env.processing_critical 1.000
```

### plugin test

``` shell
munin-run httping_localhost
```

To get the Plugin do its job, simply restart Munin

``` shell
service munin-node restart
```

## Requirements

 * httping
