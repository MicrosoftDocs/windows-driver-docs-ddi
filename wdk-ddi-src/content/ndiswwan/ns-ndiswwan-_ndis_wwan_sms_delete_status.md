---
UID: NS:ndiswwan._NDIS_WWAN_SMS_DELETE_STATUS
title: "_NDIS_WWAN_SMS_DELETE_STATUS"
author: windows-driver-content
description: The NDIS_WWAN_SMS_DELETE_STATUS structure represents the status of a deleted SMS text message.
old-location: netvista\ndis_wwan_sms_delete_status.htm
tech.root: netvista
ms.assetid: 78591487-d534-4e9e-852a-5826b8a98a9b
ms.date: 05/02/2018
ms.keywords: "*PNDIS_WWAN_SMS_DELETE_STATUS, NDIS_WWAN_SMS_DELETE_STATUS, NDIS_WWAN_SMS_DELETE_STATUS structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SMS_DELETE_STATUS, PNDIS_WWAN_SMS_DELETE_STATUS structure pointer [Network Drivers Starting with Windows Vista], WwanRef_aa4755ba-7eac-42ef-8901-170593ed60af.xml, _NDIS_WWAN_SMS_DELETE_STATUS, ndiswwan/NDIS_WWAN_SMS_DELETE_STATUS, ndiswwan/PNDIS_WWAN_SMS_DELETE_STATUS, netvista.ndis_wwan_sms_delete_status"
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
-	NDIS_WWAN_SMS_DELETE_STATUS
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_SMS_DELETE_STATUS, *PNDIS_WWAN_SMS_DELETE_STATUS
---

# _NDIS_WWAN_SMS_DELETE_STATUS structure


## -description


The NDIS_WWAN_SMS_DELETE_STATUS structure represents the status of a deleted SMS text message.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_SMS_DELETE_STATUS
     structure. The MB Service sets the header with the values that are shown in the following table when it
     sends the data structure to the miniport driver for 
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
NDIS_WWAN_SMS_DELETE_STATUS_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SMS_DELETE_STATUS)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>.


### -field uStatus

The status of the SMS delete operation.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>
 

 

