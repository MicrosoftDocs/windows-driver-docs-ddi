---
UID: NS:wwan._WWAN_SMS_CONFIGURATION
title: _WWAN_SMS_CONFIGURATION
author: windows-driver-content
description: The WWAN_SMS_CONFIGURATION structure represents the SMS configuration of the MB device.
old-location: netvista\wwan_sms_configuration.htm
old-project: netvista
ms.assetid: 85075b9d-72a7-4f3e-8a25-888689f9d5e1
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WWAN_SMS_CONFIGURATION, WWAN_SMS_CONFIGURATION, *PWWAN_SMS_CONFIGURATION
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
req.alt-api: WWAN_SMS_CONFIGURATION
req.alt-loc: wwan.h
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
req.typenames: WWAN_SMS_CONFIGURATION, *PWWAN_SMS_CONFIGURATION
req.product: Windows 10 or later.
---

# _WWAN_SMS_CONFIGURATION structure



## -description
The WWAN_SMS_CONFIGURATION structure represents the SMS configuration of the MB device.



## -syntax

````
typedef struct _WWAN_SMS_CONFIGURATION {
  CHAR            ScAddress[WWAN_SMS_ADDRESS_MAX_LEN];
  WWAN_SMS_FORMAT SmsFormat;
  ULONG           ulMaxMessageIndex;
} WWAN_SMS_CONFIGURATION, *PWWAN_SMS_CONFIGURATION;
````


## -struct-fields

### -field ScAddress

A NULL-terminated string with a maximum length of 15 digits that represents the Service Center
     (SC) address. This member is used by all text messages for sending and receiving. For PDU-style SMS
     messages, this information is used if it is not available in PDU data.
     

The number can be in any of the following formats:

<ul>
<li>
"+ &lt;International Country Code&gt; &lt;SMS Service Center Number&gt;\0"

</li>
<li>
"&lt;SMS Service Center Number&gt;\0"

</li>
</ul>
For set requests, the MB Service can set this member to <b>NULL</b>. In this case, a <b>NULL</b> indicates the
     miniport driver does not need to update the 
     <b>ScAddress</b> member and should not update this member thereafter.


### -field SmsFormat

The SMS message format that should be used for the unsolicited indication of new SMS message
     arrivals. CDMA-based devices support only the 
     <b>WwanSmsFormatCdma</b> format. The 
     <b>WwanSmsFormatCdma</b> format does not apply to GSM-based devices.


### -field ulMaxMessageIndex

The maximum number of messages that can be stored on the device. Miniport drivers report this
     value for 
     <i>query</i> requests. Unsolicited events that are used to notify the change of 
     <b>ScAddress</b> must also contain valid information for this member.


## -remarks
Miniport drivers need to fill in this data structure only when processing 
    <i>query</i> requests, or in case of unsolicited events.


## -see-also
<dl>
<dt>
<a href="..\wwan\ne-wwan-_wwan_sms_format.md">WWAN_SMS_FORMAT</a>
</dt>
<dt>
<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_sms_configuration.md">NDIS_WWAN_SMS_CONFIGURATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_SMS_CONFIGURATION structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

