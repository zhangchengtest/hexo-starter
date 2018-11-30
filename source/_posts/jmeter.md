title: 'jmeter '
date: 2017-06-06 14:46:20
tags:
---
title: 'jmeter '
tags:
---

./bin/jmeter
install plugin

https://jmeter-plugins.org/wiki/PluginsManager/

download the jar and put it to lib/ext

安装 PerfMon Metrics Collector，用来监控CPU，memory等系统资源

然后在target server上安装agent
https://jmeter-plugins.org/wiki/PerfMonAgent/

./startAgent.sh --udp-port 0 --auto-shutdown
