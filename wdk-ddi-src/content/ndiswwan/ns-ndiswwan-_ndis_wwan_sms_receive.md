---
UID: NS:ndiswwan._NDIS_WWAN_SMS_RECEIVE
title: "_NDIS_WWAN_SMS_RECEIVE"
author: windows-driver-content
description: The NDIS_WWAN_SMS_RECEIVE structure represents a list of received SMS messages and the number of messages in the list.
old-location: netvista\ndis_wwan_sms_receive.htm
old-project: netvista
ms.assetid: 2ff53520-5ba0-47dc-816d-6245924356ee
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNDIS_WWAN_SMS_RECEIVE, NDIS_WWAN_SMS_RECEIVE, NDIS_WWAN_SMS_RECEIVE structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SMS_RECEIVE, PNDIS_WWAN_SMS_RECEIVE structure pointer [Network Drivers Starting with Windows Vista], WwanRef_f268c794-63fd-4d7f-afba-67c7b232ea91.xml, _NDIS_WWAN_SMS_RECEIVE, ndiswwan/NDIS_WWAN_SMS_RECEIVE, ndiswwan/PNDIS_WWAN_SMS_RECEIVE, netvista.ndis_wwan_sms_receive"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndiswwan.h
api_name:
-	NDIS_WWAN_SMS_RECEIVE
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_SMS_RECEIVE, *PNDIS_WWAN_SMS_RECEIVE
---

# _NDIS_WWAN_SMS_RECEIVE structure


## -description


The NDIS_WWAN_SMS_RECEIVE structure represents a list of received SMS messages and the number of
  messages in the list.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_SMS_RECEIVE structure.
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
NDIS_WWAN_SMS_RECEIVE_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SMS_RECEIVE)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>.


### -field uStatus

The status of the SMS receive operation.


### -field SmsListHeader

A formatted 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571208">WWAN_LIST_HEADER</a> object that represents a
     list of received SMS messages and the number of messages in the list.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571208">WWAN_LIST_HEADER</a>
 

 

