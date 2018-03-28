---
UID: NE:wwan._WWAN_MSG_STATUS
title: "_WWAN_MSG_STATUS"
author: windows-driver-content
description: The WWAN_MSG_STATUS enumeration lists different SMS message statuses.
old-location: netvista\wwan_msg_status.htm
old-project: netvista
ms.assetid: 60eb0494-fcc6-4546-a13a-b6d1dcf165e6
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWWAN_MSG_STATUS, PWWAN_MSG_STATUS, PWWAN_MSG_STATUS enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_MSG_STATUS, WWAN_MSG_STATUS enumeration [Network Drivers Starting with Windows Vista], WwanMsgStatusDraft, WwanMsgStatusMax, WwanMsgStatusNew, WwanMsgStatusOld, WwanMsgStatusSent, WwanRef_2cd2fe07-ee6c-4193-960e-434e31561f9e.xml, _WWAN_MSG_STATUS, netvista.wwan_msg_status, wwan/PWWAN_MSG_STATUS, wwan/WWAN_MSG_STATUS, wwan/WwanMsgStatusDraft, wwan/WwanMsgStatusMax, wwan/WwanMsgStatusNew, wwan/WwanMsgStatusOld, wwan/WwanMsgStatusSent"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	WWAN_MSG_STATUS
product: Windows
targetos: Windows
req.typenames: WWAN_MSG_STATUS, *PWWAN_MSG_STATUS
req.product: Windows 10 or later.
---

# _WWAN_MSG_STATUS enumeration


## -description


The WWAN_MSG_STATUS enumeration lists different SMS message statuses.


## -enum-fields




### -field WwanMsgStatusNew

The message is new or unread.


### -field WwanMsgStatusOld

The message is old and is read.


### -field WwanMsgStatusDraft

The message is unsent and stored in the device.


### -field WwanMsgStatusSent

The message has already been sent.


### -field WwanMsgStatusMax

The total number of supported SMS message statuses.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff571243">WWAN_SMS_CDMA_RECORD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571248">WWAN_SMS_PDU_RECORD</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_MSG_STATUS enumeration%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

