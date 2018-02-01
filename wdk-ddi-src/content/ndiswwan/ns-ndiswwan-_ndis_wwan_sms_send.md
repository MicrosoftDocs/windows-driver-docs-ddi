---
UID: NS:ndiswwan._NDIS_WWAN_SMS_SEND
title: "_NDIS_WWAN_SMS_SEND"
author: windows-driver-content
description: The NDIS_WWAN_SMS_SEND structure represents an SMS message to send.
old-location: netvista\ndis_wwan_sms_send.htm
old-project: netvista
ms.assetid: d92c0ebe-4a11-49d9-95aa-182e99ca8dcf
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: WwanRef_ef75a09f-b42a-4bd6-ae59-b94d5e4b0e54.xml, netvista.ndis_wwan_sms_send, NDIS_WWAN_SMS_SEND structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SMS_SEND structure pointer [Network Drivers Starting with Windows Vista], ndiswwan/NDIS_WWAN_SMS_SEND, PNDIS_WWAN_SMS_SEND, NDIS_WWAN_SMS_SEND, _NDIS_WWAN_SMS_SEND, ndiswwan/PNDIS_WWAN_SMS_SEND, *PNDIS_WWAN_SMS_SEND
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndiswwan.h
apiname:
-	NDIS_WWAN_SMS_SEND
product: Windows
targetos: Windows
req.typenames: "*PNDIS_WWAN_SMS_SEND, NDIS_WWAN_SMS_SEND"
---

# _NDIS_WWAN_SMS_SEND structure


## -description


The NDIS_WWAN_SMS_SEND structure represents an SMS message to send.


## -syntax


````
typedef struct _NDIS_WWAN_SMS_SEND {
  NDIS_OBJECT_HEADER Header;
  WWAN_SMS_SEND      SmsSend;
} NDIS_WWAN_SMS_SEND, *PNDIS_WWAN_SMS_SEND;
````


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
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field SmsSend

A formatted 
     <a href="..\wwan\ns-wwan-_wwan_sms_send.md">WWAN_SMS_SEND</a> object that represents a SMS
     text message to send.


## -see-also

<a href="..\wwan\ns-wwan-_wwan_sms_send.md">WWAN_SMS_SEND</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_SMS_SEND structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

