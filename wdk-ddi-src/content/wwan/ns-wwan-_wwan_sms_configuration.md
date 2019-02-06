---
UID: NS:wwan._WWAN_SMS_CONFIGURATION
title: _WWAN_SMS_CONFIGURATION (wwan.h)
description: The WWAN_SMS_CONFIGURATION structure represents the SMS configuration of the MB device.
old-location: netvista\wwan_sms_configuration.htm
tech.root: netvista
ms.assetid: 85075b9d-72a7-4f3e-8a25-888689f9d5e1
ms.date: 05/02/2018
ms.keywords: "*PWWAN_SMS_CONFIGURATION, PWWAN_SMS_CONFIGURATION, PWWAN_SMS_CONFIGURATION structure pointer [Network Drivers Starting with Windows Vista], WWAN_SMS_CONFIGURATION, WWAN_SMS_CONFIGURATION structure [Network Drivers Starting with Windows Vista], WwanRef_d68f5af0-d14e-4b01-a77d-4d3fea6db828.xml, _WWAN_SMS_CONFIGURATION, netvista.wwan_sms_configuration, wwan/PWWAN_SMS_CONFIGURATION, wwan/WWAN_SMS_CONFIGURATION"
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
-	WWAN_SMS_CONFIGURATION
product:
- Windows
targetos: Windows
req.typenames: WWAN_SMS_CONFIGURATION, *PWWAN_SMS_CONFIGURATION
---

# _WWAN_SMS_CONFIGURATION structure


## -description


The WWAN_SMS_CONFIGURATION structure represents the SMS configuration of the MB device.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567935">NDIS_WWAN_SMS_CONFIGURATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571247">WWAN_SMS_FORMAT</a>
 

 

