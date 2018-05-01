---
UID: NS:ndiswwan._NDIS_WWAN_SET_DEVICE_SLOT_MAPPING_INFO
title: "_NDIS_WWAN_SET_DEVICE_SLOT_MAPPING_INFO"
author: windows-driver-content
description: The NDIS_WWAN_SET_DEVICE_SLOT_MAPPING_INFO structure sets the executor-to-slot mapping relationship of the MB device.
old-location: netvista\ndis_wwan_set_device_slot_mappings.htm
old-project: netvista
ms.assetid: 5DAE5A36-1A2B-46DF-8CF1-FAC8B98460A8
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PNDIS_WWAN_SET_DEVICE_SLOT_MAPPING_INFO, NDIS_WWAN_SET_DEVICE_SLOT_MAPPING_INFO, NDIS_WWAN_SET_DEVICE_SLOT_MAPPING_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SET_DEVICE_SLOT_MAPPING_INFO, PNDIS_WWAN_SET_DEVICE_SLOT_MAPPING_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_SET_DEVICE_SLOT_MAPPING_INFO, ndiswwan/NDIS_WWAN_SET_DEVICE_SLOT_MAPPING_INFO, ndiswwan/PNDIS_WWAN_SET_DEVICE_SLOT_MAPPING_INFO, netvista.ndis_wwan_set_device_slot_mappings"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	NDIS_WWAN_SET_DEVICE_SLOT_MAPPING_INFO
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_SET_DEVICE_SLOT_MAPPING_INFO, *PNDIS_WWAN_SET_DEVICE_SLOT_MAPPING_INFO
---

# _NDIS_WWAN_SET_DEVICE_SLOT_MAPPING_INFO structure


## -description


The <b>NDIS_WWAN_SET_DEVICE_SLOT_MAPPING_INFO</b> structure sets the executor-to-slot mapping relationship of the MB device.


## -struct-fields




### -field Header

The header with type, revision, and size information about the <b>NDIS_WWAN_SET_DEVICE_SLOT_MAPPINGS</b> structure.
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
NDIS_WWAN_SET_DEVICE_SLOT_MAPPING_INFO_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SET_DEVICE_SLOT_MAPPING_INFO)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>.


### -field SetDeviceSlotMappingInfo

 




#### - DeviceSlotMappings

A formatted <a href="https://msdn.microsoft.com/48DD867C-1235-4955-A01E-FF46C850DA31">WWAN_DEVICE_SLOT_MAPPING_INFO</a> structure that represents the executor-to-slot mapping relationship of the MB device.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/54AF3447-7918-49CE-945A-DC8DC1E78CBF">OID_WWAN_DEVICE_SLOT_MAPPING_INFO</a>



<a href="https://msdn.microsoft.com/48DD867C-1235-4955-A01E-FF46C850DA31">WWAN_DEVICE_SLOT_MAPPING_INFO</a>
 

 

