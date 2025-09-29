Updated Home Assistant YAML for SHxxT Inverters. Tested on SH15/20/25T so far.
- Connection via Logger port with RS485 to Ethernet adaptor recommended. WiNet untested at this stage.

Notes below:
1) No need for secrets file. To configure, set IP on line 4, Port on line 5 & Device Address on Line 11.
2) Multiple Inverters can be configured with a simple find/replace: "inv1" -> "inv2" etc
3) All inverter min/max values are automatically calcualted and applied
4) Sungrow SBR/SBH Battery Config is auto calculated
5) Most modbus calls are combined into multi register requests to minimise bus blocking chatter
6) Many extra registers have been reverse engineered
7) New Automation Format to make the code simpler to read
8) New Number Template formatting again for Simpler Code
9) Extensive use of Yaml Anchors to minimise duplication
10) Many options have been combined to simplify UI elements

Also included is YAML for reading all known registers (and many new) for SBR batteries. SBH is mostly done also but still a WIP, need more testers.
-This isn't as polished as the Inverter code, needs more work to be drop in if you don't know what you're doing.
-The relevant code will need to be integrated to your main sungrow yaml so this is intended as notes only.
-The per module data IS NOT available via WiNet (it blocks those registers).

Happy to take requests for further register discovery that iSolarCloud provide, that aren't yet in HA.
Open to testing on other inverter models... but unless you know what you're doing and don't mind troubleshooting I recommend staying away for now.
Need testers via WiNet ( Assume some registers aren't available )

If you're moving from another system, be sure to delete all entities and statistics or HA will mess up the naming.

Feedback welcome
