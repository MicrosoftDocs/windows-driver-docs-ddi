---
UID: NS:ndiswwan._NDIS_WWAN_SMS_DELETE
title: "_NDIS_WWAN_SMS_DELETE"
author: windows-driver-content
description: The NDIS_WWAN_SMS_DELETE structure represents an SMS message to delete.
old-location: netvista\ndis_wwan_sms_delete.htm
tech.root: netvista
ms.assetid: ea13c900-40b2-492b-b14b-85e346208ad8
ms.date: 5/2/2018
ms.keywords: "*PNDIS_WWAN_SMS_DELETE, NDIS_WWAN_SMS_DELETE, NDIS_WWAN_SMS_DELETE structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SMS_DELETE, PNDIS_WWAN_SMS_DELETE structure pointer [Network Drivers Starting with Windows Vista], WwanRef_aae03f3f-21d1-42d4-b2dd-008fc07c9964.xml, _NDIS_WWAN_SMS_DELETE, ndiswwan/NDIS_WWAN_SMS_DELETE, ndiswwan/PNDIS_WWAN_SMS_DELETE, netvista.ndis_wwan_sms_delete"
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
-	NDIS_WWAN_SMS_DELETE
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_SMS_DELETE, *PNDIS_WWAN_SMS_DELETE
---

# _NDIS_WWAN_SMS_DELETE structure


## -description


The NDIS_WWAN_SMS_DELETE structure represents an SMS message to delete.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_SMS_DELETE structure. The
     MB Service sets the header with the values that are shown in the following table when it sends the data
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
NDIS_WWAN_SMS_DELETE_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SMS_DELETE)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>.


### -field SmsFilter

A formatted 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571245">WWAN_SMS_FILTER</a> object that represents the
     filter to apply to SMS messages.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571245">WWAN_SMS_FILTER</a>
 

 

