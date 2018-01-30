---
UID: NS:wwan._WWAN_SET_SMS_CONFIGURATION
title: "_WWAN_SET_SMS_CONFIGURATION"
author: windows-driver-content
description: The WWAN_SET_SMS_CONFIGURATION structure represents how MB devices support SMS configuration.
old-location: netvista\wwan_set_sms_configuration.htm
old-project: netvista
ms.assetid: c3739a08-f4ea-4cc5-8f62-7d4a5cd3ed43
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: WwanRef_2a344216-b18f-41d6-8a11-dac6cb24de69.xml, WWAN_SET_SMS_CONFIGURATION structure [Network Drivers Starting with Windows Vista], netvista.wwan_set_sms_configuration, WWAN_SET_SMS_CONFIGURATION, wwan/WWAN_SET_SMS_CONFIGURATION, PWWAN_SET_SMS_CONFIGURATION structure pointer [Network Drivers Starting with Windows Vista], wwan/PWWAN_SET_SMS_CONFIGURATION, _WWAN_SET_SMS_CONFIGURATION, *PWWAN_SET_SMS_CONFIGURATION, PWWAN_SET_SMS_CONFIGURATION
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
-	WWAN_SET_SMS_CONFIGURATION
product: Windows
targetos: Windows
req.typenames: WWAN_SET_SMS_CONFIGURATION, *PWWAN_SET_SMS_CONFIGURATION
req.product: Windows 10 or later.
---

# _WWAN_SET_SMS_CONFIGURATION structure


## -description


The WWAN_SET_SMS_CONFIGURATION structure represents how MB devices support SMS configuration.


## -syntax


````
typedef struct _WWAN_SET_SMS_CONFIGURATION {
  CHAR            ScAddress[WWAN_SMS_ADDRESS_MAX_LEN];
  WWAN_SMS_FORMAT SmsFormat;
} WWAN_SET_SMS_CONFIGURATION, *PWWAN_SET_SMS_CONFIGURATION;
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
</ul>For 
     <i>set</i> requests, the MB Service can set this member to <b>NULL</b>. In this case, a <b>NULL</b> indicates the
     miniport driver does not need to update 
     <b>ScAddress</b> and should not update this member thereafter.


### -field SmsFormat

The SMS message format that should be used for the unsolicited indication of new SMS message
     arrivals. CDMA-based devices support only 
     <b>WwanSmsFormatCdma</b> format. The 
     <b>WwanSmsFormatCdma</b> format is does not apply to GSM-based devices.


## -see-also

<a href="..\wwan\ne-wwan-_wwan_sms_format.md">WWAN_SMS_FORMAT</a>

<mshelp:link keywords="netvista.ndis_wwan_set_sms_configuration" tabindex="0"><b>
   NDIS_WWAN_SET_SMS_CONFIGURATION</b></mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_SET_SMS_CONFIGURATION structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

