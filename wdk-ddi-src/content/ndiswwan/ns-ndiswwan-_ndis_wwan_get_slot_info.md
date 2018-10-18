---
UID: NS:ndiswwan._NDIS_WWAN_GET_SLOT_INFO
title: "_NDIS_WWAN_GET_SLOT_INFO"
author: windows-driver-content
description: The NDIS_WWAN_GET_SLOT_INFO structure represents the status of a slot in the modem of the MB device.
old-location: netvista\ndis_wwan_get_slot_info_status.htm
tech.root: netvista
ms.assetid: 214AFAD3-B211-4D66-8CFC-58F8EB407B83
ms.date: 05/02/2018
ms.keywords: "*PNDIS_WWAN_GET_SLOT_INFO, NDIS_WWAN_GET_SLOT_INFO, NDIS_WWAN_GET_SLOT_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_GET_SLOT_INFO, PNDIS_WWAN_GET_SLOT_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_GET_SLOT_INFO, ndiswwan/NDIS_WWAN_GET_SLOT_INFO, ndiswwan/PNDIS_WWAN_GET_SLOT_INFO, netvista.ndis_wwan_get_slot_info_status"
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
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
-	ndiswwan.h
api_name:
-	NDIS_WWAN_GET_SLOT_INFO
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_GET_SLOT_INFO, *PNDIS_WWAN_GET_SLOT_INFO
---

# _NDIS_WWAN_GET_SLOT_INFO structure


## -description


The <b>NDIS_WWAN_GET_SLOT_INFO</b> structure represents the status of a slot in the modem of the MB device.


## -struct-fields




### -field Header

The header with type, revision, and size information about the <b>NDIS_WWAN_GET_SLOT_INFO</b> structure.
     The MB Service sets the header with the values that are shown in the following table when it sends the
     data structure to the miniport driver for 
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
NDIS_WWAN_GET_SLOT_INFO_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_GET_SLOT_INFO)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>.


### -field GetSlotInfo

 




#### - SlotInfoStatus

A formatted <a href="https://msdn.microsoft.com/62955CA4-8631-4A85-8E78-5A91A9DA0069">WWAN_GET_SLOT_INFO</a> structure which contains the slot index to specify which slot's status the query request is for.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/62955CA4-8631-4A85-8E78-5A91A9DA0069">WWAN_GET_SLOT_INFO</a>
 

 

