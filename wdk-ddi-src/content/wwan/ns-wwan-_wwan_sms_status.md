---
UID: NS:wwan._WWAN_SMS_STATUS
title: "_WWAN_SMS_STATUS"
author: windows-driver-content
description: The WWAN_SMS_STATUS structure represents the status of the SMS message store.
old-location: netvista\wwan_sms_status.htm
tech.root: netvista
ms.assetid: a7ebe58d-8e87-437f-b556-408610fa654e
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: "*PWWAN_SMS_STATUS, PWWAN_SMS_STATUS, PWWAN_SMS_STATUS structure pointer [Network Drivers Starting with Windows Vista], WWAN_SMS_STATUS, WWAN_SMS_STATUS structure [Network Drivers Starting with Windows Vista], WwanRef_5468242f-eb44-4ece-92a2-02524eb0d196.xml, _WWAN_SMS_STATUS, netvista.wwan_sms_status, wwan/PWWAN_SMS_STATUS, wwan/WWAN_SMS_STATUS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
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
-	wwan.h
api_name:
-	WWAN_SMS_STATUS
product:
- Windows
targetos: Windows
req.typenames: WWAN_SMS_STATUS, *PWWAN_SMS_STATUS
---

# _WWAN_SMS_STATUS structure


## -description


The WWAN_SMS_STATUS structure represents the status of the SMS message store.


## -struct-fields




### -field uFlag

A bitmap of flags that represent the status of the message store on the MB device. The values for 
     <b>uFlag</b> are defined in the following table.
     

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WWAN_SMS_FLAG_NONE

</td>
<td>
No status to report.

</td>
</tr>
<tr>
<td>
WWAN_SMS_FLAG_MESSAGE_STORE_FULL

</td>
<td>
The message store is full.

</td>
</tr>
<tr>
<td>
WWAN_SMS_FLAG_NEW_MESSAGE

</td>
<td>
A new, non-Class 0 (flash/alert) message has arrived.

</td>
</tr>
</table>
 

Miniport drivers should not set or clear any flag until a change of state occurs. For example, the
     WWAN_SMS_FLAG_MESSAGE_STORE_FULL flag must remain set until the miniport driver completely processes a
     delete message request that comes from the MB Service. Similarly, the WWAN_SMS_FLAG_NEW_MESSAGE flag
     must remain set until the miniport driver completely processes a read new message request from the MB
     Service.

Miniport drivers must send an unsolicited event to the MB Service whenever a flag is set. Miniport
     drivers do not need to send an unsolicited event when a flag is cleared (reset).


### -field MessageIndex

This is the index of the newly arrived message or the recently arrived message in case of a 
     <i>query</i> response.
     

Unique index into the message store between 1 and 
     <b>ulMaxMessageIndex</b> returned in NDIS_STATUS_WWAN_SMS_CONFIGURATION.

If the 
     <b>uFlag</b> is not set with WWAN_SMS_NEW_MESSAGE, this member must be initialized by the miniport driver
     with WWAN_MESSAGE_INDEX_NONE.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567945">NDIS_WWAN_SMS_STATUS</a>
 

 

