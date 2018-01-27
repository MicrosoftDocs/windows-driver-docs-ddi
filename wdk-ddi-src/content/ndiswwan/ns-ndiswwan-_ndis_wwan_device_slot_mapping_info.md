---
UID: NS:ndiswwan._NDIS_WWAN_DEVICE_SLOT_MAPPING_INFO
title: _NDIS_WWAN_DEVICE_SLOT_MAPPING_INFO
author: windows-driver-content
description: The NDIS_WWAN_DEVICE_SLOT_MAPPING_INFO structure represents the executor-to-slot mapping relationship of the MB device.
old-location: netvista\ndis_wwan_device_slot_mappings.htm
old-project: netvista
ms.assetid: 18437B56-B84C-499B-8D4F-F65B5B8221A6
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: _NDIS_WWAN_DEVICE_SLOT_MAPPING_INFO, PNDIS_WWAN_DEVICE_SLOT_MAPPING_INFO, ndiswwan/PNDIS_WWAN_DEVICE_SLOT_MAPPING_INFO, NDIS_WWAN_DEVICE_SLOT_MAPPING_INFO, PNDIS_WWAN_DEVICE_SLOT_MAPPING_INFO structure pointer [Network Drivers Starting with Windows Vista], netvista.ndis_wwan_device_slot_mappings, NDIS_WWAN_DEVICE_SLOT_MAPPING_INFO structure [Network Drivers Starting with Windows Vista], ndiswwan/NDIS_WWAN_DEVICE_SLOT_MAPPING_INFO, *PNDIS_WWAN_DEVICE_SLOT_MAPPING_INFO
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
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	ndiswwan.h
apiname: 
-	NDIS_WWAN_DEVICE_SLOT_MAPPING_INFO
product: Windows
targetos: Windows
req.typenames: *PNDIS_WWAN_DEVICE_SLOT_MAPPING_INFO, NDIS_WWAN_DEVICE_SLOT_MAPPING_INFO
---

# _NDIS_WWAN_DEVICE_SLOT_MAPPING_INFO structure


## -description


The <b>NDIS_WWAN_DEVICE_SLOT_MAPPING_INFO</b> structure represents the executor-to-slot mapping relationship of the MB device.


## -syntax


````
typedef struct _NDIS_WWAN_DEVICE_SLOT_MAPPING_INFO {
  NDIS_OBJECT_HEADER            Header;
  WWAN_STATUS                   uStatus;
  WWAN_DEVICE_SLOT_MAPPING_INFO DeviceSlotMappings;
} NDIS_WWAN_DEVICE_SLOT_MAPPING_INFO, *PNDIS_WWAN_DEVICE_SLOT_MAPPING_INFO;
````


## -struct-fields




### -field Header

The header with type, revision, and size information about the <b>NDIS_WWAN_DEVICE_SLOT_MAPPING_INFO</b> structure.
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
NDIS_WWAN_DEVICE_SLOT_MAPPING_INFO_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_DEVICE_SLOT_MAPPING_INFO)

</td>
</tr>
</table> 

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field uStatus

The system capability status. The following table shows the possible values for
     this member.
     
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WWAN_STATUS_SUCCESS

</td>
<td>
The operation succeeded.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_BUSY

</td>
<td>
The operation failed because the device was busy. In the absence of any explicit information from the function to clear this condition, the host can use subsequent actions by the function (e.g. notifications or command completions) as a hint to retry the failed operation.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_FAILURE

</td>
<td>
The operation failed.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_INVALID_PARAMETERS

</td>
<td>
The operation failed because of invalid parameters (e.g. slot numbers out of range or duplicated values in the mapping).

</td>
</tr>
<tr>
<td>
WWAN_STATUS_NO_DEVICE_SUPPORT

</td>
<td>
The operation failed because the device does not support this OID.

</td>
</tr>
</table> 


### -field DeviceSlotMappingInfo

 



#### - DeviceSlotMappings

A formatted <a href="..\wwan\ns-wwan-_wwan_device_slot_mapping_info.md">WWAN_DEVICE_SLOT_MAPPING_INFO</a> structure that represents the executor-to-slot mapping relationship of the MB device.


## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

<a href="..\wwan\ns-wwan-_wwan_device_slot_mapping_info.md">WWAN_DEVICE_SLOT_MAPPING_INFO</a>

<a href="https://msdn.microsoft.com/54AF3447-7918-49CE-945A-DC8DC1E78CBF">OID_WWAN_DEVICE_SLOT_MAPPING_INFO</a>

<a href="https://msdn.microsoft.com/7825C20E-FB56-420D-B516-1ADA0C7C382E">NDIS_STATUS_WWAN_DEVICE_SLOT_MAPPING_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_DEVICE_SLOT_MAPPING_INFO structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

