---
title: RDP Usage
description: |
    Track Remote Desktop Protocol logons to target machines
location: |
    Win7/8/10:
    %SYSTEM ROOT%\System32\winevt\logs\Security.evtx
    %SYSTEM ROOT%\System32\winevt\logs\Microsoft-Windows-RemoteDesktopServices-RdpCoreTS%4Operational.evtx
    %SYSTEM ROOT%\System32\winevt\logs\Microsoft-Windows-TerminalServices-RemoteConnectionManager%4Operational.evtx
    %SYSTEM ROOT%\System32\winevt\logs\Microsoft-Windows-TerminalServices-LocalSessionManager%4Operational.evtx
interpretation: |
    * Security.evtx
        * Win7/8/10 – Interpretation
            * Event ID 4778 – Session Connected/Reconnected
            * Event ID 4779 – Session Disconnected
            * Event ID 4624 Logon Type 10
        * Event log provides hostname (beside 4624) and IP address of remote
            machine making the connection
        * On workstations you will often see current console session
            disconnected (4779) followed by RDP connection (4778)
    * Microsoft-Windows-RemoteDesktopServices-RdpCoreTS%4Operational.evtx
        * Interpretation
            * Event ID 131 - Connection Attempts
                * Contains source IP and Logon Username
            * Event ID 98 - Succesfull Connections
    * Microsoft-Windows-TerminalServices-RemoteConnectionManager%4Operational.evtx
        * Interpretation
            * Event ID 1149 - User authentication succeeded
                * Contains source IP and Logon Username
    * Microsoft-Windows-TerminalServices-LocalSessionManager%4Operational.evtx
        * Interpretation
            * Event ID 21 - Session logon succeeded
                * Contains source IP and Logon Username
            * Event ID 22 - Shell start notification received
                * Contains source IP and Logon Username
            * Event ID 25 - Session reconnection succeeded
                * Contains source IP and Logon Username
            * Event ID 41 - Begin session arbitration
                * Contains Logon Username
evids-categories:
  - accountusage
---
