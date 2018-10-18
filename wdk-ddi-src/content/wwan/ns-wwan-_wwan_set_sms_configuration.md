---
UID: NS:wwan._WWAN_SET_SMS_CONFIGURATION
title: "_WWAN_SET_SMS_CONFIGURATION"
author: windows-driver-content
description: The WWAN_SET_SMS_CONFIGURATION structure represents how MB devices support SMS configuration.
old-location: netvista\wwan_set_sms_configuration.htm
tech.root: netvista
ms.assetid: c3739a08-f4ea-4cc5-8f62-7d4a5cd3ed43
ms.date: 5/2/2018
ms.keywords: "*PWWAN_SET_SMS_CONFIGURATION, PWWAN_SET_SMS_CONFIGURATION, PWWAN_SET_SMS_CONFIGURATION structure pointer [Network Drivers Starting with Windows Vista], WWAN_SET_SMS_CONFIGURATION, WWAN_SET_SMS_CONFIGURATION structure [Network Drivers Starting with Windows Vista], WwanRef_2a344216-b18f-41d6-8a11-dac6cb24de69.xml, _WWAN_SET_SMS_CONFIGURATION, netvista.wwan_set_sms_configuration, wwan/PWWAN_SET_SMS_CONFIGURATION, wwan/WWAN_SET_SMS_CONFIGURATION"
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
-	WWAN_SET_SMS_CONFIGURATION
product:
- Windows
targetos: Windows
req.typenames: WWAN_SET_SMS_CONFIGURATION, *PWWAN_SET_SMS_CONFIGURATION
---

# _WWAN_SET_SMS_CONFIGURATION structure


## -description


The WWAN_SET_SMS_CONFIGURATION structure represents how MB devices support SMS configuration.


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
For 
     <i>set</i> requests, the MB Service can set this member to <b>NULL</b>. In this case, a <b>NULL</b> indicates the
     miniport driver does not need to update 
     <b>ScAddress</b> and should not update this member thereafter.


### -field SmsFormat

The SMS message format that should be used for the unsolicited indication of new SMS message
     arrivals. CDMA-based devices support only 
     <b>WwanSmsFormatCdma</b> format. The 
     <b>WwanSmsFormatCdma</b> format is does not apply to GSM-based devices.


## -see-also




<a href="https://msdn.microsoft.com/aa191c47-4b3b-464a-8a12-db673fca0f20">
   NDIS_WWAN_SET_SMS_CONFIGURATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571247">WWAN_SMS_FORMAT</a>
 

 

