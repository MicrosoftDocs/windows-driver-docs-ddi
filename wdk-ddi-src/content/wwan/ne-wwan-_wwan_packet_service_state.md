---
UID: NE:wwan._WWAN_PACKET_SERVICE_STATE
title: "_WWAN_PACKET_SERVICE_STATE"
author: windows-driver-content
description: The WWAN_PACKET_SERVICE_STATE enumeration lists the different packet service attachment states that are supported by the MB device.
old-location: netvista\wwan_packet_service_state.htm
old-project: netvista
ms.assetid: 542a8a3b-7704-434c-ad81-0cf8e1f70015
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PWWAN_PACKET_SERVICE_STATE, PWWAN_PACKET_SERVICE_STATE, PWWAN_PACKET_SERVICE_STATE enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_PACKET_SERVICE_STATE, WWAN_PACKET_SERVICE_STATE enumeration [Network Drivers Starting with Windows Vista], WwanPacketServiceStateAttached, WwanPacketServiceStateAttaching, WwanPacketServiceStateDetached, WwanPacketServiceStateDetaching, WwanPacketServiceStateUnknown, WwanRef_c342b0ee-c3da-4199-9172-4e2fb538f64b.xml, _WWAN_PACKET_SERVICE_STATE, netvista.wwan_packet_service_state, wwan/PWWAN_PACKET_SERVICE_STATE, wwan/WWAN_PACKET_SERVICE_STATE, wwan/WwanPacketServiceStateAttached, wwan/WwanPacketServiceStateAttaching, wwan/WwanPacketServiceStateDetached, wwan/WwanPacketServiceStateDetaching, wwan/WwanPacketServiceStateUnknown"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wwan.h
api_name:
-	WWAN_PACKET_SERVICE_STATE
product: Windows
targetos: Windows
req.typenames: WWAN_PACKET_SERVICE_STATE, *PWWAN_PACKET_SERVICE_STATE
---

# _WWAN_PACKET_SERVICE_STATE enumeration


## -description


The WWAN_PACKET_SERVICE_STATE enumeration lists the different packet service attachment states that
  are supported by the MB device.


## -enum-fields




### -field WwanPacketServiceStateUnknown

Packet service state is unknown. The miniport driver should specify this state on a failure to set
     the MB packet service state.


### -field WwanPacketServiceStateAttaching

Packet service attach action is in progress.


### -field WwanPacketServiceStateAttached

Packet service is attached.


### -field WwanPacketServiceStateDetaching

Packet service detach action is in progress.


### -field WwanPacketServiceStateDetached

Packet service is detached.


## -remarks



The packet service attach or detach state is typically reflected in the device's user interface.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff571210">WWAN_PACKET_SERVICE</a>
 

 

