---
UID: NE:fwpsk.FWPS_PACKET_INJECTION_STATE_
title: FWPS_PACKET_INJECTION_STATE_
author: windows-driver-content
description: The FWPS_PACKET_INJECTION_STATE enumeration type specifies the injection state of a network buffer list.
old-location: netvista\fwps_packet_injection_state.htm
old-project: netvista
ms.assetid: 0fc60bae-2191-4e19-85c5-ed06f09225f0
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: FWPS_PACKET_INJECTED_BY_OTHER, FWPS_PACKET_INJECTED_BY_SELF, FWPS_PACKET_INJECTION_STATE, FWPS_PACKET_INJECTION_STATE enumeration [Network Drivers Starting with Windows Vista], FWPS_PACKET_INJECTION_STATE_, FWPS_PACKET_INJECTION_STATE_MAX, FWPS_PACKET_NOT_INJECTED, FWPS_PACKET_PREVIOUSLY_INJECTED_BY_SELF, fwpsk/FWPS_PACKET_INJECTED_BY_OTHER, fwpsk/FWPS_PACKET_INJECTED_BY_SELF, fwpsk/FWPS_PACKET_INJECTION_STATE, fwpsk/FWPS_PACKET_INJECTION_STATE_MAX, fwpsk/FWPS_PACKET_NOT_INJECTED, fwpsk/FWPS_PACKET_PREVIOUSLY_INJECTED_BY_SELF, netvista.fwps_packet_injection_state, wfp_ref_4_enum_d8d574f4-6323-43e0-924f-09639f6aec10.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows Vista.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fwpsk.h
api_name:
-	FWPS_PACKET_INJECTION_STATE
product: Windows
targetos: Windows
req.typenames: FWPS_PACKET_INJECTION_STATE
---

# FWPS_PACKET_INJECTION_STATE_ enumeration


## -description


The FWPS_PACKET_INJECTION_STATE enumeration type specifies the injection state of a network buffer
  list.


## -enum-fields




### -field FWPS_PACKET_NOT_INJECTED

The packet was not injected by any of the 
     <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff545018">packet injection functions</a>. A
     packet that originated from the TCP/IP stack will be at this state.


### -field FWPS_PACKET_INJECTED_BY_SELF

The packet was injected using an injection handle passed by a call to one of the 
     <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff545018">packet injection functions</a>.


### -field FWPS_PACKET_INJECTED_BY_OTHER

The packet was injected using an injection handle other than one passed by a call
     to one of the 
     <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff545018">packet injection functions</a>.


### -field FWPS_PACKET_PREVIOUSLY_INJECTED_BY_SELF

The packet was injected by using an injection handle passed by a call to one of the
     
     <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff545018">packet injection functions</a>, but
     the packet was later cloned and reinjected by an additional call to a packet injection function,
     possibly using a different injection handle.


### -field FWPS_PACKET_INJECTION_STATE_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.

