---
UID: NE:netadapter._NET_ADAPTER_MEDIA_SPECIFIC_WAKEUP_EVENTS_FLAGS
title: _NET_ADAPTER_MEDIA_SPECIFIC_WAKEUP_EVENTS_FLAGS (netadapter.h)
description: Specifies the media-specific wake-up events that a network adapter supports.
tech.root: netvista
ms.assetid: 73fcfbf5-e5c4-4ee3-9ed5-544b743e683c
ms.date: 02/05/2018
ms.topic: enum
ms.keywords: _NET_ADAPTER_MEDIA_SPECIFIC_WAKEUP_EVENTS_FLAGS, NET_ADAPTER_MEDIA_SPECIFIC_WAKEUP_EVENTS_FLAGS, 
req.header: netadapter.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.alt-api:
req.alt-loc:
req.typenames: NET_ADAPTER_MEDIA_SPECIFIC_WAKEUP_EVENTS_FLAGS
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netadapter.h
apiname: 
-	NET_ADAPTER_MEDIA_SPECIFIC_WAKEUP_EVENTS_FLAGS
product:
-	Windows
targetos: Windows
product:
- Windows
---

# _NET_ADAPTER_MEDIA_SPECIFIC_WAKEUP_EVENTS_FLAGS enumeration

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

Specifies the media-specific wake-up events that a network adapter supports.

## -enum-fields

### -field NET_ADAPTER_WLAN_WAKE_ON_NLO_DISCOVERY : 
If this flag is set, the 802.11 network adapter can generate a wake-up event if it detects a service set identifier (SSID) that was specified through a network list offload (NLO). 

For more information about NLO, see [Wi-Fi Network List Offload](https://docs.microsoft.com/windows-hardware/drivers/network/wi-fi-network-list-offload).

### -field NET_ADAPTER_WLAN_WAKE_ON_AP_ASSOCIATION_LOST : 
If this flag is set, the 802.11 network adapter can generate a wake-up event if it disassociates with the access point (AP).

### -field NET_ADAPTER_WLAN_WAKE_ON_GTK_HANDSHAKE_ERROR : 
If this flag is set, the 802.11 network adapter can generate a wake-up event if it encounters an error during the IEEE 802.11i RSN group transient key (GTK) handshake with the AP.

### -field NET_ADAPTER_WLAN_WAKE_ON_4WAY_HANDSHAKE_REQUEST : 
If this flag is set, the 802.11 network adapter can generate a wake-up event if it receives the first frame of the IEEE 802.11i RSN 4-way handshake with the AP. This handshake is performed when the adapter authenticates with the AP.

### -field NET_ADAPTER_WWAN_WAKE_ON_REGISTER_STATE : 
If this flag is set, the mobile broadband (MB) network adapter can generate a wake-up event if its registration state to the MB Service has changed.

### -field NET_ADAPTER_WWAN_WAKE_ON_SMS_RECEIVE : 
If this flag is set, the MB network adapter can generate a wake-up event if the MB Service has to be notified about the receipt of a Short Message Service (SMS) message. The adapter generates this wake-up event either after the completion of a previously issued OID_WWAN_SMS_READ query request, or the arrival of a new class-0 (flash/alert) message from the network provider as an event notification.

### -field NET_ADAPTER_WWAN_WAKE_ON_USSD_RECEIVE : 
If this flag is set, the MB network adapter can generate a wake-up event if it receives an Unstructured Supplementary Service Data (USSD) message.

### -field NET_ADAPTER_WWAN_WAKE_ON_PACKET_STATE : 
If this flag is set, the MB network adapter can generate a wake-up event when the Packet Service state of the Modem changes.

### -field NET_ADAPTER_WWAN_WAKE_ON_UICC_CHANGE : 
If this flag is set, the MB network adapter can generate a wake-up event when the UICC (SIM) is inserted or removed. 

## -remarks

The **NET_ADAPTER_MEDIA_SPECIFIC_WAKEUP_EVENTS_FLAGS** enumeration is used to specify supported media-specific wake-up events in the [NET_ADAPTER_POWER_CAPABILITIES](ns-netadapter-_net_adapter_power_capabilities.md) structure.

The [NET_ADAPTER_POWER_CAPABILITIES](ns-netadapter-_net_adapter_power_capabilities.md) structure is used as input to [NetAdapterSetPowerCapabilities](nf-netadapter-netadaptersetpowercapabilities.md).



## -see-also

[NET_ADAPTER_POWER_CAPABILITIES](ns-netadapter-_net_adapter_power_capabilities.md)

[NetAdapterSetPowerCapabilities](nf-netadapter-netadaptersetpowercapabilities.md)
