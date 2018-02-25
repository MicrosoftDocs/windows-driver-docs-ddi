---
UID: NS:wwan._WWAN_SMS_STATUS
title: "_WWAN_SMS_STATUS"
author: windows-driver-content
description: The WWAN_SMS_STATUS structure represents the status of the SMS message store.
old-location: netvista\wwan_sms_status.htm
old-project: netvista
ms.assetid: a7ebe58d-8e87-437f-b556-408610fa654e
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PWWAN_SMS_STATUS, ,, A, M, N, P, PWWAN_SMS_STATUS, PWWAN_SMS_STATUS structure pointer [Network Drivers Starting with Windows Vista], S, T, U, W, WWAN_SMS_STATUS, WWAN_SMS_STATUS structure [Network Drivers Starting with Windows Vista], WwanRef_5468242f-eb44-4ece-92a2-02524eb0d196.xml, _, _WWAN_SMS_STATUS, netvista.wwan_sms_status, wwan/PWWAN_SMS_STATUS, wwan/WWAN_SMS_STATUS"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wwan.h
apiname:
-	WWAN_SMS_STATUS
product: Windows
targetos: Windows
req.typenames: WWAN_SMS_STATUS, *PWWAN_SMS_STATUS
req.product: Windows 10 or later.
---

# _WWAN_SMS_STATUS structure


## -description


The WWAN_SMS_STATUS structure represents the status of the SMS message store.


## -syntax


````
typedef struct _WWAN_SMS_STATUS {
  ULONG uFlag;
  ULONG MessageIndex;
} WWAN_SMS_STATUS, *PWWAN_SMS_STATUS;
````


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

<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_sms_status.md">NDIS_WWAN_SMS_STATUS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_SMS_STATUS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

