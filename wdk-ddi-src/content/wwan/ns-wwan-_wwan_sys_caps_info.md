---
UID: NS:wwan._WWAN_SYS_CAPS_INFO
title: "_WWAN_SYS_CAPS_INFO"
author: windows-driver-content
description: The WWAN_SYS_CAPS_INFO structure represents the modem's system capability.
old-location: netvista\wwan_sys_caps.htm
old-project: netvista
ms.assetid: EBD9D4CA-E032-4BB3-A802-D2D7A39E9A42
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWWAN_SYS_CAPS_INFO, PWWAN_SYS_CAPS_INFO, PWWAN_SYS_CAPS_INFO structure pointer [Network Drivers Starting with Windows Vista], WWAN_SYS_CAPS_INFO, WWAN_SYS_CAPS_INFO structure [Network Drivers Starting with Windows Vista], _WWAN_SYS_CAPS_INFO, netvista.wwan_sys_caps, wwan/PWWAN_SYS_CAPS_INFO, wwan/WWAN_SYS_CAPS_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
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
product: Windows
targetos: Windows
req.typenames: WWAN_SYS_CAPS_INFO, *PWWAN_SYS_CAPS_INFO
req.product: Windows 10 or later.
---

# _WWAN_SYS_CAPS_INFO structure


## -description


The <b>WWAN_SYS_CAPS_INFO</b> structure represents the modem's system capability.


## -syntax


````
typedef struct WWAN_SYS_CAPS_INFO {
  ULONG  NumberOfExecutors;
  ULONG  NumberOfSlots;
  ULONG  Concurrency;
  UINT64 ModemID;
} WWAN_SYS_CAPS_INFO, *PWWAN_SYS_CAPS_INFO;
````


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

<a href="https://msdn.microsoft.com/D158432A-A715-4ABB-969C-F8F80D2DB845">OID_WWAN_SYS_CAPS_INFO</a>



<a href="https://msdn.microsoft.com/653A35EC-29BB-458D-B33C-41EF6EF47A6E">NDIS_STATUS_WWAN_SYS_CAPS_INFO</a>



<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_sys_caps_info.md">NDIS_WWAN_SYS_CAPS_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_SYS_CAPS_INFO structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

