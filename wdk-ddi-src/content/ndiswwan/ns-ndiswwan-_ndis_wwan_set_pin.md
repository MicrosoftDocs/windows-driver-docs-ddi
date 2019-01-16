---
UID: NS:ndiswwan._NDIS_WWAN_SET_PIN
title: "_NDIS_WWAN_SET_PIN"
description: The NDIS_WWAN_SET_PIN structure represents what PIN action to take on the MB device.
old-location: netvista\ndis_wwan_set_pin.htm
tech.root: netvista
ms.assetid: 96c85e4d-d31d-4e89-9822-2c9068533b9a
ms.date: 05/02/2018
ms.keywords: "*PNDIS_WWAN_SET_PIN, NDIS_WWAN_SET_PIN, NDIS_WWAN_SET_PIN structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SET_PIN, PNDIS_WWAN_SET_PIN structure pointer [Network Drivers Starting with Windows Vista], WwanRef_565f6200-b5cd-4845-a606-bfb098eda610.xml, _NDIS_WWAN_SET_PIN, ndiswwan/NDIS_WWAN_SET_PIN, ndiswwan/PNDIS_WWAN_SET_PIN, netvista.ndis_wwan_set_pin"
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
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
-	ndiswwan.h
api_name:
-	NDIS_WWAN_SET_PIN
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_SET_PIN, *PNDIS_WWAN_SET_PIN
---

# _NDIS_WWAN_SET_PIN structure


## -description


The NDIS_WWAN_SET_PIN structure represents what PIN action to take on the MB device.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_SET_PIN structure. The MB
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
NDIS_WWAN_SET_PIN_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SET_PIN)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>.


### -field PinAction

A formatted 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571213">WWAN_PIN_ACTION</a> object that represents an
     action to perform with a Personal Identification Number (PIN).


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571213">WWAN_PIN_ACTION</a>
 

 

