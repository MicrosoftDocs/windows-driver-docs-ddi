---
UID: NE:dot11wificxtypes._WDI_CONNECTION_QUALITY_HINT
tech.root: netvista
title: WDI_CONNECTION_QUALITY_HINT (dot11wificxtypes.h)
ms.date: 07/23/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_CONNECTION_QUALITY_HINT enumeration defines the Wi-Fi connection quality hints.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dot11wificxtypes.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dot11wificxtypes.h
api_name:
 - _WDI_CONNECTION_QUALITY_HINT
 - WDI_CONNECTION_QUALITY_HINT
f1_keywords:
 - _WDI_CONNECTION_QUALITY_HINT
 - dot11wificxtypes/_WDI_CONNECTION_QUALITY_HINT
 - WDI_CONNECTION_QUALITY_HINT
 - dot11wificxtypes/WDI_CONNECTION_QUALITY_HINT
dev_langs:
 - c++
---

## -description

The **WDI_CONNECTION_QUALITY_HINT** enumeration defines the Wi-Fi connection quality hints.

## -enum-fields

### -field WDI_CONNECTION_QUALITY_AUTO_POWER_SAVE:1

This hint indicates that the host has no specific preference for the usage of this port. The port should use power saving mechanisms when possible, as well as when other ports require a larger share of bandwidth/radio time. It can be enabled simultaneously on more than one port. This is the default Connection Quality setting for a port.

### -field WDI_CONNECTION_QUALITY_LOW_LATENCY:2

This hint indicates that the host wants to use this port for low latency operations. The adapter should provide service to this port at a regular interval.

The WLAN schedule should be such that one-way latency is no more than 30ms, packet loss is \<=0.5%, and no more than 3 consecutive packets are lost. It should also honor the off-channel latency requirements specified.

This can be set simultaneously on two ports. If the ports are on different channels, the max latency is relaxed to 50ms. This is based on Windows Certification Program requirements.

When in this mode, the port can (optionally) use power saving as long as it can meet the above latency requirements. Additionally, when a port is in this mode, the adapter should avoid unnecessary scans. If the adapter needs to perform scans that are not triggered by Microsoft components, it should optimize the scan to meet the requirements of the off-channel time. For this, it can limit the scan to a single off channel at a time.

When a port is in this mode, during roaming the adapter should optimize the AP selection (for example, using different link quality thresholds to not scan or roam too often), the association process (for example, by using cached TSF for synchronization), and security exchange (for example, being more aggressive about using PMKIDs).

### -field WDI_CONNECTION_QUALITY_HIGH_THROUGHPUT:3

This hint indicates that the host is performing an operation on the port which is not tolerant to packet loss. The adapter should not power save and should remain on the given port’s operational channel for as long as possible without losing link connectivity on other ports, until this connection quality hint is unset.

This may be set due to L2 protocol (EAP/4-way handshake exchanges/etc), L3 protocol (DHCP/etc.), or other scenarios where high channel availability is important to the overall experience.

This can only be set on one port.

### -field WDI_CONNECTION_QUALITY_NO_POWER_SAVE:4

This hint indicates that the host does not want the adapter to perform any power saving. There are not specific requirements for data path performance.

## -remarks

The **WDI_CONNECTION_QUALITY_HINT** enumeration is a value in the [**WDI_TLV_FTM_RESPONSE**](/windows-hardware/drivers/netcx/wdi-tlv-connection-quality-parameters) TLV.

## -see-also

[**WDI_TLV_FTM_RESPONSE**](/windows-hardware/drivers/netcx/wdi-tlv-connection-quality-parameters)