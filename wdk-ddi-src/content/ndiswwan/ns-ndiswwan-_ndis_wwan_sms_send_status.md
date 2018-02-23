---
UID: NS:ndiswwan._NDIS_WWAN_SMS_SEND_STATUS
title: "_NDIS_WWAN_SMS_SEND_STATUS"
author: windows-driver-content
description: The NDIS_WWAN_SMS_SEND_STATUS structure represents the status of a sent SMS text message.
old-location: netvista\ndis_wwan_sms_send_status.htm
old-project: netvista
ms.assetid: 2664fed3-c1fb-4f84-b265-d1b0d8a0ca04
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: WwanRef_5ca36240-d372-4887-887f-8b2b209a5c8a.xml, PNDIS_WWAN_SMS_SEND_STATUS, ndiswwan/NDIS_WWAN_SMS_SEND_STATUS, NDIS_WWAN_SMS_SEND_STATUS structure [Network Drivers Starting with Windows Vista], NDIS_WWAN_SMS_SEND_STATUS, ndiswwan/PNDIS_WWAN_SMS_SEND_STATUS, *PNDIS_WWAN_SMS_SEND_STATUS, _NDIS_WWAN_SMS_SEND_STATUS, netvista.ndis_wwan_sms_send_status, PNDIS_WWAN_SMS_SEND_STATUS structure pointer [Network Drivers Starting with Windows Vista]
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
-	NDIS_WWAN_SMS_SEND_STATUS
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_SMS_SEND_STATUS, *PNDIS_WWAN_SMS_SEND_STATUS
---

# _NDIS_WWAN_SMS_SEND_STATUS structure


## -description


The NDIS_WWAN_SMS_SEND_STATUS structure represents the status of a sent SMS text message.


## -syntax


````
typedef struct _NDIS_WWAN_SMS_SEND_STATUS {
  NDIS_OBJECT_HEADER Header;
  WWAN_STATUS        uStatus;
  ULONG              MessageReference;
} NDIS_WWAN_SMS_SEND_STATUS, *PNDIS_WWAN_SMS_SEND_STATUS;
````


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
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field uStatus

The status of the SMS send operation.


### -field MessageReference

A reference number that is returned upon successful delivery of the SMS text message. This member
     is populated by the device only if 
     <b>uStatus</b> member is set to WWAN_STATUS_SUCCESS.


## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_SMS_SEND_STATUS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

