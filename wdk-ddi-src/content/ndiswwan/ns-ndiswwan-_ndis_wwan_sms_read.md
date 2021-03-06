---
UID: NS:ndiswwan._NDIS_WWAN_SMS_READ
title: _NDIS_WWAN_SMS_READ (ndiswwan.h)
description: The NDIS_WWAN_SMS_READ structure represents an SMS message to read.
old-location: netvista\ndis_wwan_sms_read.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_WWAN_SMS_READ structure"]
ms.keywords: "*PNDIS_WWAN_SMS_READ, NDIS_WWAN_SMS_READ, NDIS_WWAN_SMS_READ structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SMS_READ, PNDIS_WWAN_SMS_READ structure pointer [Network Drivers Starting with Windows Vista], WwanRef_7264d34b-78a0-4537-a386-bd77d210d7ae.xml, _NDIS_WWAN_SMS_READ, ndiswwan/NDIS_WWAN_SMS_READ, ndiswwan/PNDIS_WWAN_SMS_READ, netvista.ndis_wwan_sms_read"
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
req.typenames: NDIS_WWAN_SMS_READ, *PNDIS_WWAN_SMS_READ
f1_keywords:
 - _NDIS_WWAN_SMS_READ
 - ndiswwan/_NDIS_WWAN_SMS_READ
 - PNDIS_WWAN_SMS_READ
 - ndiswwan/PNDIS_WWAN_SMS_READ
 - NDIS_WWAN_SMS_READ
 - ndiswwan/NDIS_WWAN_SMS_READ
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - _NDIS_WWAN_SMS_READ
 - PNDIS_WWAN_SMS_READ
 - NDIS_WWAN_SMS_READ
---

# _NDIS_WWAN_SMS_READ structure


## -description

The NDIS_WWAN_SMS_READ structure represents an SMS message to read.

## -struct-fields

### -field Header

The header with type, revision, and size information about the NDIS_WWAN_SMS_READ structure. The
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
NDIS_WWAN_SMS_READ_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SMS_READ)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="/windows-hardware/drivers/ddi/objectheader/ns-objectheader-ndis_object_header">NDIS_OBJECT_HEADER</a>.

### -field SmsRead

A formatted 
     <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_sms_read">WWAN_SMS_READ</a> object that represents the
     format and filter of SMS messages to read.

## -see-also

<a href="/windows-hardware/drivers/ddi/objectheader/ns-objectheader-ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_sms_read">WWAN_SMS_READ</a>

