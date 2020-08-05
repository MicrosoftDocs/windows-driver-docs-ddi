---
UID: NS:ndiswwan._NDIS_WWAN_SMS_SEND
title: _NDIS_WWAN_SMS_SEND (ndiswwan.h)
description: The NDIS_WWAN_SMS_SEND structure represents an SMS message to send.
old-location: netvista\ndis_wwan_sms_send.htm
tech.root: netvista
ms.assetid: d92c0ebe-4a11-49d9-95aa-182e99ca8dcf
ms.date: 05/02/2018
keywords: ["NDIS_WWAN_SMS_SEND structure"]
ms.keywords: "*PNDIS_WWAN_SMS_SEND, NDIS_WWAN_SMS_SEND, NDIS_WWAN_SMS_SEND structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SMS_SEND, PNDIS_WWAN_SMS_SEND structure pointer [Network Drivers Starting with Windows Vista], WwanRef_ef75a09f-b42a-4bd6-ae59-b94d5e4b0e54.xml, _NDIS_WWAN_SMS_SEND, ndiswwan/NDIS_WWAN_SMS_SEND, ndiswwan/PNDIS_WWAN_SMS_SEND, netvista.ndis_wwan_sms_send"
f1_keywords:
 - "ndiswwan/NDIS_WWAN_SMS_SEND"
 - "NDIS_WWAN_SMS_SEND"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndiswwan.h
api_name:
- NDIS_WWAN_SMS_SEND
targetos: Windows
req.typenames: NDIS_WWAN_SMS_SEND, *PNDIS_WWAN_SMS_SEND
---

# _NDIS_WWAN_SMS_SEND structure


## -description


The NDIS_WWAN_SMS_SEND structure represents an SMS message to send.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_SMS_SEND structure. The
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
NDIS_WWAN_SMS_SEND_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SMS_SEND)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.


### -field SmsSend

A formatted 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_sms_send">WWAN_SMS_SEND</a> object that represents a SMS
     text message to send.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_sms_send">WWAN_SMS_SEND</a>
 

 

