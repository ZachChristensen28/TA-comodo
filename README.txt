### Technology Add-on for the Comodo Firewall ###

   Author: Zach Christensen

   Version/Date: 1.0.0 04/20/2019

   Supported product(s):
                   Comodo Firewall 11 on Windows 10


   Source types:
                comodo:client:config
                comodo:client:cmd
                comodo:client:hips
                comodo:client:file
                comodo:client:firewall
                comodo:client:task


   Comodo Firewall Requirements:
                                Ensure the Comodo firewall is writing to the Windows event logs.
                                General Settings > Logging > (check box for "Write to Windows Event Log")


   Input requirements:
                      Use the WinEventLog stanza in inputs.conf and set source type to comodo for the comodo logs you wish to monitor. (Check Event Viewer under Application and Server logs)
                      i.e.

                      ## inputs.conf

                      [WinEventLog://COMODO Client - Security CEF]
                      disabled = 0
                      sourcetype = comodo

                      [WinEventLog://COMODO Internet Security CEF]
                      disabled = 0
                      sourcetype = comodo

                      [WinEventLog://COMODO Internet Security Trace]
                      disabled = 0
                      sourcetype = comodo


                      https://docs.splunk.com/Documentation/Splunk/latest/Admin/Inputsconf#Windows_Event_Log_Monitor

   Where to Install this add-on:
                                Search Heads         : Yes
                                Indexers             : Conditional
                                Heavy Forwarders     : Conditional
                                Universal Forwarders : No
                                ** Must be installed on either the HF or Indexers **

   ### Bugs ###

   Please open an issue at https://github.com/ZachChristensen28/TA-comodo
