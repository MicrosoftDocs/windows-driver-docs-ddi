---
UID: NS:wwan._WWAN_PROVIDER2
title: _WWAN_PROVIDER2 (wwan.h)
description: The WWAN_PROVIDER2 structure describes the details of a network provider.
old-location: netvista\wwan_provider2.htm
tech.root: netvista
ms.assetid: 0B9352EE-C7CE-4F9D-9373-0096222295A4
ms.date: 05/02/2018
keywords: ["WWAN_PROVIDER2 structure"]
ms.keywords: "*PWWAN_PROVIDER2, PWWAN_PROVIDER2, PWWAN_PROVIDER2 structure pointer [Network Drivers Starting with Windows Vista], WWAN_PROVIDER2, WWAN_PROVIDER2 structure [Network Drivers Starting with Windows Vista], _WWAN_PROVIDER2, netvista.wwan_provider2, wwan/PWWAN_PROVIDER2, wwan/WWAN_PROVIDER2"
f1_keywords:
 - "wwan/WWAN_PROVIDER2"
 - "WWAN_PROVIDER2"
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows 8 and later versions of Windows.
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wwan.h
api_name:
- WWAN_PROVIDER2
targetos: Windows
req.typenames: WWAN_PROVIDER2, *PWWAN_PROVIDER2
---

# _WWAN_PROVIDER2 structure


## -description


The WWAN_PROVIDER2 structure describes the details of a network provider.


## -struct-fields




### -field Provider

A formatted WWAN_PROVIDER object that represents details about a network provider.


### -field WwanCellularClass

The cellular class that the provider uses.


### -field Rssi

A value that represents the strength of the wireless signal. Please refer to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_signal_state">WWAN_SIGNAL_STATE</a> on the format of this member.


### -field ErrorRate

	A coded value that represents a percentage range of error rates. Please refer to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_signal_state">WWAN_SIGNAL_STATE</a> on the format of this member.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ne-wwan-_wwan_cellular_class">WWAN_CELLULAR_CLASS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_provider">WWAN_PROVIDER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_signal_state">WWAN_SIGNAL_STATE</a>
 

 

