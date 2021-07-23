---
UID: NE:dot11wificxtypes._WDI_P2P_LISTEN_STATE
tech.root: netvista
title: WDI_P2P_LISTEN_STATE (dot11wificxtypes.h)
ms.date: 07/22/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_P2P_LISTEN_STATE enumeration defines the Wi-Fi Direct listen states.
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
 - _WDI_P2P_LISTEN_STATE
 - WDI_P2P_LISTEN_STATE
f1_keywords:
 - _WDI_P2P_LISTEN_STATE
 - dot11wificxtypes/_WDI_P2P_LISTEN_STATE
 - WDI_P2P_LISTEN_STATE
 - dot11wificxtypes/WDI_P2P_LISTEN_STATE
dev_langs:
 - c++
---


## -description

The WDI_P2P_LISTEN_STATE enumeration defines the Wi-Fi Direct listen states.

## -enum-fields

### -field WDI_P2P_LISTEN_STATE_OFF

When this listen state is set:

* The port shall not schedule any time to explicitly listen on social channels for incoming Wi-Fi Direct action frames.
* The port shall not respond to probe requests as a Wi-Fi Direct Adapter.

### -field WDI_P2P_LISTEN_STATE_PASSIVE_AVAILABILITY

When this listen state is set:

* The port must enter into listen state periodically as specified by the ListenDuration parameters.
* The port shall respond to probe requests with a "DIRECT-" SSID as a Wi-Fi Direct Adapter when parked on the specified channel.

### -field WDI_P2P_LISTEN_STATE_AUTOMATIC_AVAILABILITY

When this listen state is set:

* The port must schedule time to explicitly listen on a social channel for incoming Wi-Fi Direct action frames.
* The port shall respond to probe requests with a "DIRECT-" SSID as a Wi-Fi Direct Adapter when parked on the configured social channel.

> [!NOTE] The optimized duty cycle for automatic availability listen state is outside the scope of this specification. The most aggressive power saving schedule that may be implemented by the port is being available for a contiguous 500ms out of every 5 seconds.

### -field WDI_P2P_LISTEN_STATE_HIGH_AVAILABILITY

When this listen state is set:

* The port must schedule time to explicitly listen on a social channel for incoming Wi-Fi Direct action frames.
* The port shall respond to probe requests with a "DIRECT-" SSID as a Wi-Fi Direct Adapter when parked on the configured social channel.
> [!NOTE] The duty cycle for this listen state is 300ms availability every 400ms on the configured social channel.

## -remarks

This enumeration is a value in the [**WDI_TLV_P2P_LISTEN_STATE**](/windows-hardware/drivers/netcx/wdi-tlv-p2p-listen-state) TLV.

## -see-also

[**WDI_TLV_P2P_LISTEN_STATE**](/windows-hardware/drivers/netcx/wdi-tlv-p2p-listen-state)