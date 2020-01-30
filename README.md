# barracuda-waf-syslog-ng-influxdb-parser
Parse Barracuda WAF access/firewall logs via syslog-ng and Telegraf to be stored in Influxdb

<b>This is a script collection to enable log parsing from Barracuda WAF into InfluxDB</b>

Solutions used:
Barracuda Web Application Firewall with configured Syslog log export
Syslog-ng with configuration to rewrite and pass log data to Telegraf
Telegraf agent to parse the logs and split kv pairs into Influx tags and fields*
Grafana for visualizing the data

*Data can be transferred directly from Syslog-ng to InfluxDB skipping Telegraf, but depending on workloads, you may face big quantities of data being transferred, flooding InfluxDB. Syslog-ng have throttling mechanisms, but I prefer the native support from Telegraf.
