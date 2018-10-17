---
UID: NS:wwan._WWAN_SYS_CAPS_INFO
title: "_WWAN_SYS_CAPS_INFO"
author: windows-driver-content
description: The WWAN_SYS_CAPS_INFO structure represents the modem's system capability.
old-location: netvista\wwan_sys_caps.htm
tech.root: netvista
ms.assetid: EBD9D4CA-E032-4BB3-A802-D2D7A39E9A42
ms.date: 5/2/2018
ms.keywords: "*PWWAN_SYS_CAPS_INFO, PWWAN_SYS_CAPS_INFO, PWWAN_SYS_CAPS_INFO structure pointer [Network Drivers Starting with Windows Vista], WWAN_SYS_CAPS_INFO, WWAN_SYS_CAPS_INFO structure [Network Drivers Starting with Windows Vista], _WWAN_SYS_CAPS_INFO, netvista.wwan_sys_caps, wwan/PWWAN_SYS_CAPS_INFO, wwan/WWAN_SYS_CAPS_INFO"
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1703
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
-	WWAN_SYS_CAPS_INFO
product:
- Windows
targetos: Windows
req.typenames: WWAN_SYS_CAPS_INFO, *PWWAN_SYS_CAPS_INFO
---

# _WWAN_SYS_CAPS_INFO structure


## -description


The <b>WWAN_SYS_CAPS_INFO</b> structure represents the modem's system capability.


## -struct-fields




### -field NumberOfExecutors

Denotes the number of <i>executors</i> (MBB instances) that are supported by the modem in its current configuration.


### -field NumberOfSlots

Denotes the number of slots that are physically present on the modem. Each slot reported must be capable of receiving a UICC card; the slots themselves can be a heterogeneous mix if needed - mini SIM, micro SIM, nano SIM, or any standard as defined by ETSI. The number of slots <b>must</b> be at least equal to or greater than the number of executors supported. The "greater than" provision allows for the use of non-telephony UICC cards (such as for security, NFC, etc.).


### -field Concurrency

Denotes the number of executors that may be active at the same time, where 1 ≤ Concurrency ≤ NumberOfExecutors. For example, a dual-standby modem would have a <b>Concurrency</b> of 1 while a dual-active modem would have a <b>Concurrency</b> of 2.


### -field ModemID

A unique 64-bit number that identifies the modem. This is required to distinguish one modem from others if there is more than one modem present in a device. The modem ID should be constant across reboots or device removal and insertion.


## -see-also




<a href="https://msdn.microsoft.com/653A35EC-29BB-458D-B33C-41EF6EF47A6E">NDIS_STATUS_WWAN_SYS_CAPS_INFO</a>



<a href="https://msdn.microsoft.com/6A4963A0-4724-4709-A940-817B8AEBE1C9">NDIS_WWAN_SYS_CAPS_INFO</a>



<a href="https://msdn.microsoft.com/D158432A-A715-4ABB-969C-F8F80D2DB845">OID_WWAN_SYS_CAPS_INFO</a>
 

 

