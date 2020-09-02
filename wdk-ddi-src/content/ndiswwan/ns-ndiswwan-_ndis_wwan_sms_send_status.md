---
UID: NS:ndiswwan._NDIS_WWAN_SMS_SEND_STATUS
title: _NDIS_WWAN_SMS_SEND_STATUS (ndiswwan.h)
description: The NDIS_WWAN_SMS_SEND_STATUS structure represents the status of a sent SMS text message.
old-location: netvista\ndis_wwan_sms_send_status.htm
tech.root: netvista
ms.assetid: 2664fed3-c1fb-4f84-b265-d1b0d8a0ca04
ms.date: 05/02/2018
keywords: ["NDIS_WWAN_SMS_SEND_STATUS structure"]
ms.keywords: "*PNDIS_WWAN_SMS_SEND_STATUS, NDIS_WWAN_SMS_SEND_STATUS, NDIS_WWAN_SMS_SEND_STATUS structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SMS_SEND_STATUS, PNDIS_WWAN_SMS_SEND_STATUS structure pointer [Network Drivers Starting with Windows Vista], WwanRef_5ca36240-d372-4887-887f-8b2b209a5c8a.xml, _NDIS_WWAN_SMS_SEND_STATUS, ndiswwan/NDIS_WWAN_SMS_SEND_STATUS, ndiswwan/PNDIS_WWAN_SMS_SEND_STATUS, netvista.ndis_wwan_sms_send_status"
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
targetos: Windows
req.typenames: NDIS_WWAN_SMS_SEND_STATUS, *PNDIS_WWAN_SMS_SEND_STATUS
f1_keywords:
 - _NDIS_WWAN_SMS_SEND_STATUS
 - ndiswwan/_NDIS_WWAN_SMS_SEND_STATUS
 - PNDIS_WWAN_SMS_SEND_STATUS
 - ndiswwan/PNDIS_WWAN_SMS_SEND_STATUS
 - NDIS_WWAN_SMS_SEND_STATUS
 - ndiswwan/NDIS_WWAN_SMS_SEND_STATUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - NDIS_WWAN_SMS_SEND_STATUS
---

# _NDIS_WWAN_SMS_SEND_STATUS structure


## -description

The NDIS_WWAN_SMS_SEND_STATUS structure represents the status of a sent SMS text message.

## -struct-fields

### -field Header

The header with type, revision, and size information about the NDIS_WWAN_SMS_SEND_STATUS
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
NDIS_WWAN_SMS_SEND_STATUS_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SMS_SEND_STATUS)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.

### -field uStatus

The status of the SMS send operation.

### -field MessageReference

A reference number that is returned upon successful delivery of the SMS text message. This member
     is populated by the device only if 
     <b>uStatus</b> member is set to WWAN_STATUS_SUCCESS.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>

