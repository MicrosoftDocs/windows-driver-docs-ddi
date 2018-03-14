---
UID: NA:netpowersettings
ms.assetid: b8e5f183-7059-3894-b4fe-bb5b6b4cf813
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Netpowersettings.h header



This header is used by Networking drivers for Windows Vista and later. For more information, see
- [Networking drivers for Windows Vista and later](../_netvista/index.md)

Netpowersettings.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [NetPowerSettingsGetEnabledMediaSpecificWakeUpEvents function](nf-netpowersettings-netpowersettingsgetenabledmediaspecificwakeupevents.md) | Retrieves flags that specify currently enabled media-specific wake-up events that a network adapter supports. |
| [NetPowerSettingsGetEnabledProtocolOffloadFlags function](nf-netpowersettings-netpowersettingsgetenabledprotocoloffloadflags.md) | Retrieves flags that specify currently enabled low power protocol offloads that a network adapter supports. |
| [NetPowerSettingsGetEnabledWakePatternFlags function](nf-netpowersettings-netpowersettingsgetenabledwakepatternflags.md) | Retrieves flags representing currently enabled wake pattern types that a network adapter supports. |
| [NetPowerSettingsGetEnabledWakeUpFlags function](nf-netpowersettings-netpowersettingsgetenabledwakeupflags.md) | Retrieves flags that specify currently enabled media-independent wake-up events that a network adapter supports. |
| [NetPowerSettingsGetProtocolOffload function](nf-netpowersettings-netpowersettingsgetprotocoloffload.md) | Retrieves a structure that specifies parameters for a low power protocol offload to a network adapter. |
| [NetPowerSettingsGetProtocolOffloadCount function](nf-netpowersettings-netpowersettingsgetprotocoloffloadcount.md) | Retrieves the number of protocol offload structures associated with a NETPOWERSETTINGS object. |
| [NetPowerSettingsGetProtocolOffloadCountForType function](nf-netpowersettings-netpowersettingsgetprotocoloffloadcountfortype.md) | Retrieves the number of protocol offload structures in the NETPOWERSETTINGS object for the particular offload type. |
| [NetPowerSettingsGetWakePattern function](nf-netpowersettings-netpowersettingsgetwakepattern.md) | Retrieves the wake pattern structure at the specified index. |
| [NetPowerSettingsGetWakePatternCount function](nf-netpowersettings-netpowersettingsgetwakepatterncount.md) | Retrieves the number of wake-on-LAN (WoL) patterns stored in a NETPOWERSETTINGS object. |
| [NetPowerSettingsGetWakePatternCountForType function](nf-netpowersettings-netpowersettingsgetwakepatterncountfortype.md) | Retrieves the number of wake-on-LAN (WoL) patterns stored in the NETPOWERSETTINGS object for the specified wake pattern type. |
| [NetPowerSettingsIsProtocolOffloadEnabled function](nf-netpowersettings-netpowersettingsisprotocoloffloadenabled.md) | Determines if a protocol offload is enabled. |
| [NetPowerSettingsIsWakePatternEnabled function](nf-netpowersettings-netpowersettingsiswakepatternenabled.md) | Determines if a wake-on-LAN (WoL) pattern is enabled for a network adapter. |
