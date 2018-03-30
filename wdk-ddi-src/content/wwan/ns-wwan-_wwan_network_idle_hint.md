---
UID: NS:wwan._WWAN_NETWORK_IDLE_HINT
title: "_WWAN_NETWORK_IDLE_HINT"
author: windows-driver-content
description: The WWAN_NETWORK_IDLE_HINT structure contains a hint for the network interface regarding whether data is expected to be active or idle on the interface.
old-location: netvista\wwan_network_idle_hint.htm
old-project: netvista
ms.assetid: 954DE5B5-F08F-4805-8CA0-8C42CB1750FA
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWWAN_NETWORK_IDLE_HINT, PWWAN_NETWORK_IDLE_HINT, PWWAN_NETWORK_IDLE_HINT structure pointer [Network Drivers Starting with Windows Vista], WWAN_NETWORK_IDLE_HINT, WWAN_NETWORK_IDLE_HINT structure [Network Drivers Starting with Windows Vista], _WWAN_NETWORK_IDLE_HINT, netvista.wwan_network_idle_hint, wwan/PWWAN_NETWORK_IDLE_HINT, wwan/WWAN_NETWORK_IDLE_HINT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10 and later versions of Windows.
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
-	WWAN_NETWORK_IDLE_HINT
product: Windows
targetos: Windows
req.typenames: WWAN_NETWORK_IDLE_HINT, *PWWAN_NETWORK_IDLE_HINT
req.product: Windows 10 or later.
---

# _WWAN_NETWORK_IDLE_HINT structure


## -description


The WWAN_NETWORK_IDLE_HINT structure contains a hint for the network interface regarding whether data is expected to be active or idle on the interface.


## -struct-fields




### -field IsEnabled

If TRUE, this is a hint that the network interface should utilize mechanisms for entering lower power modes faster. If FALSE, it is a hint that the network interface not utilize mechanisms for entering lower power modes faster.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn931088">NDIS_WWAN_NETWORK_IDLE_HINT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn931089">OID_WWAN_NETWORK_IDLE_HINT</a>
 

 

