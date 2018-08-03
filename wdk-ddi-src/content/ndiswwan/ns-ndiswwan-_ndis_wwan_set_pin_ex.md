---
UID: NS:ndiswwan._NDIS_WWAN_SET_PIN_EX
title: "_NDIS_WWAN_SET_PIN_EX"
author: windows-driver-content
description: The NDIS_WWAN_SET_PIN_EX structure represents what PIN action to take on the MB device.
old-location: netvista\ndis_wwan_set_pin_ex.htm
tech.root: netvista
ms.assetid: F08180ED-DC5A-4DA0-A42A-48511BC63DF8
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: "*PNDIS_WWAN_SET_PIN_EX, NDIS_WWAN_SET_PIN_EX, NDIS_WWAN_SET_PIN_EX structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SET_PIN_EX, PNDIS_WWAN_SET_PIN_EX structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_SET_PIN_EX, ndiswwan/NDIS_WWAN_SET_PIN_EX, ndiswwan/PNDIS_WWAN_SET_PIN_EX, netvista.ndis_wwan_set_pin_ex"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndiswwan.h
api_name:
-	NDIS_WWAN_SET_PIN_EX
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_SET_PIN_EX, *PNDIS_WWAN_SET_PIN_EX
---

# _NDIS_WWAN_SET_PIN_EX structure


## -description


The NDIS_WWAN_SET_PIN_EX structure represents what PIN action to take on the MB device.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_SET_PIN_EX structure. The MB
     Service sets the header with the values that are shown in the following table when it sends the data
     structure to the miniport driver for 
     <i>set</i> operations. Miniport drivers must set the header with the same values when they send the data
     structure to the MB service.
     

<table>
<tr>
<th>Header submember</th>
<th>Value</th>
</tr>
<tr>
<td>
Type

</td>
<td>
NDIS_OBJECT_TYPE_DEFAULT

</td>
</tr>
<tr>
<td>
Revision

</td>
<td>
NDIS_WWAN_SET_PIN_REVISION_2

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SET_PIN_EX)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>.


### -field PinAction

A formatted WWAN_PIN_ACTION object that represents an action to perform with a Personal Identification Number (PIN).


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff571213">WWAN_PIN_ACTION</a>
 

 

