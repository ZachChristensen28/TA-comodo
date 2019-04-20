# TA-comodo
Splunk add-on for Comodo Firewall

## Sourcetypes
- comodo:client:config
- comodo:client:cmd
- comodo:client:hips
- comodo:client:file
- comodo:client:firewall
- comodo:client:task

## Comodo Firewall Requirements
- Ensure the Comodo firewall is writing to the Windows Event Logs. (General Settings > Logging > [Check box for "Write to Windows Event Log"])

## Installation
Download this app from splunkbase or [Github](https://github.com/ZachChristensen28/TA-comodo).

### Where to Install
Splunk platform Instance type | Supported | Required | Actions required/ Comments
----------------------------- | --------- | -------- | --------------------------
Search Heads | Yes | Yes | Install this add-on to all search heads
Indexers | Yes | Conditional | Not required if you use heavy forwarders to collect data.
Heavy Forwarders | Yes | Conditional | Not required. This add-on must be installed on either the HF or Indexers.

## Input Requirements
This add-on uses the WinEventLog stanza in inputs.conf. See the [splunk documentation](https://docs.splunk.com/Documentation/Splunk/latest/Admin/Inputsconf#Windows_Event_Log_Monitor) for more information. The sourcetype must be set to "comodo" for this add-on to work.

Check the event viewer under Application and Server logs for the events you wish to monitor.

i.e.

```
# sample inputs.conf

[WinEventLog://COMODO Client - Security CEF]
disabled = 0
sourcetype = comodo

[WinEventLog://COMODO Internet Security CEF]
disabled = 0
sourcetype = comodo

[WinEventLog://COMODO Internet Security Trace]
disabled = 0
sourcetype = comodo
```

## Bugs
Please open an issue at [github.com](https://github.com/ZachChristensen28/TA-comodo)
