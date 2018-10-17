---
UID: NS:wwan._WWAN_SMS_READ
title: "_WWAN_SMS_READ"
author: windows-driver-content
description: The WWAN_SMS_READ structure represents the format and filter of SMS messages to read.
old-location: netvista\wwan_sms_read.htm
tech.root: netvista
ms.assetid: 920ca041-7fc8-4c6b-bc1a-7bf41dffcf7b
ms.date: 5/2/2018
ms.keywords: "*PWWAN_SMS_READ, PWWAN_SMS_READ, PWWAN_SMS_READ structure pointer [Network Drivers Starting with Windows Vista], WWAN_SMS_READ, WWAN_SMS_READ structure [Network Drivers Starting with Windows Vista], WwanRef_8b221a53-0311-4ed7-a98b-e8677cb40051.xml, _WWAN_SMS_READ, netvista.wwan_sms_read, wwan/PWWAN_SMS_READ, wwan/WWAN_SMS_READ"
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
-	WWAN_SMS_READ
product:
- Windows
targetos: Windows
req.typenames: WWAN_SMS_READ, *PWWAN_SMS_READ
---

# _WWAN_SMS_READ structure


## -description


The WWAN_SMS_READ structure represents the format and filter of SMS messages to read.


## -struct-fields




### -field SmsFormat

The format in which the miniport driver should return messages for 
     <i>query</i> requests. The MB Service specifies this value.
     

<b>WwanSmsFormatCdma</b> applies only to CDMA-based devices. CDMA-based devices support only the 
     <b>WwanSmsFormatCdma</b> format.


### -field ReadFilter

Represents the filter upon which the miniport driver should retrieve the messages. For example,
     the filter could indicate to return all messages in the index based on the message store, or all
     messages based on 
     <b>new</b>, 
     <b>old</b>, 
     <b>draft</b>, or 
     <b>sent</b> flags.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567941">NDIS_WWAN_SMS_READ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571245">WWAN_SMS_FILTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571247">WWAN_SMS_FORMAT</a>
 

 

