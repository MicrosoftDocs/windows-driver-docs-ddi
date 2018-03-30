---
UID: NE:wwan._WWAN_SMS_FORMAT
title: "_WWAN_SMS_FORMAT"
author: windows-driver-content
description: The WWAN_SMS_FORMAT enumeration lists different Short Message Service (SMS) formats.
old-location: netvista\wwan_sms_format.htm
old-project: netvista
ms.assetid: fb583ded-8292-4486-8e85-3d3039611d14
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWWAN_SMS_FORMAT, PWWAN_SMS_FORMAT, PWWAN_SMS_FORMAT enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_SMS_FORMAT, WWAN_SMS_FORMAT enumeration [Network Drivers Starting with Windows Vista], WwanRef_594a5286-7ead-4877-939c-ed4bf2eb99e0.xml, WwanSmsFormatCdma, WwanSmsFormatMax, WwanSmsFormatPdu, WwanSmsFormatReserved0, WwanSmsFormatReserved1, WwanSmsFormatReserved2, _WWAN_SMS_FORMAT, netvista.wwan_sms_format, wwan/PWWAN_SMS_FORMAT, wwan/WWAN_SMS_FORMAT, wwan/WwanSmsFormatCdma, wwan/WwanSmsFormatMax, wwan/WwanSmsFormatPdu, wwan/WwanSmsFormatReserved0, wwan/WwanSmsFormatReserved1, wwan/WwanSmsFormatReserved2"
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
-	WWAN_SMS_FORMAT
product: Windows
targetos: Windows
req.typenames: WWAN_SMS_FORMAT, *PWWAN_SMS_FORMAT
req.product: Windows 10 or later.
---

# _WWAN_SMS_FORMAT enumeration


## -description


The WWAN_SMS_FORMAT enumeration lists different Short Message Service (SMS) formats.


## -enum-fields




### -field WwanSmsFormatPdu

SMS messages are in PDU format. For GSM-based devices, messages are hexadecimal strings that
     represent messages in PDU format as defined in the 3GPP TS 27.005 and 3GPP TS 23.040 specifications. For
     CDMA-based devices messages are byte arrays that represent messages as defined in section 3.4.2.1 SMS
     Point-to-Point Message in 3GPP2 specification C.S0015-A "Short Message Service (SMS) for Wideband Spread
     Spectrum Systems".


### -field WwanSmsFormatReserved0

This value is reserved for future use. Do not use.


### -field WwanSmsFormatReserved1

This value is reserved for future use. Do not use.


### -field WwanSmsFormatReserved2

This value is reserved for future use. Do not use.


### -field WwanSmsFormatCdma

The message is in text format. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571243">WWAN_SMS_CDMA_RECORD</a> and 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571251">WWAN_SMS_SEND_CDMA</a>. This value applies
     only to CDMA-based devices.


### -field WwanSmsFormatMax

This value is reserved. Do not use.


## -remarks



CDMA-based devices support only 
    <b>WwanSmsFormatCdma</b>. The 
    <b>WwanSmsFormatCdma</b> format is not applicable for GSM-based devices.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff571238">WWAN_SET_SMS_CONFIGURATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571243">WWAN_SMS_CDMA_RECORD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571244">WWAN_SMS_CONFIGURATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571249">WWAN_SMS_READ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571250">WWAN_SMS_SEND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571251">WWAN_SMS_SEND_CDMA</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_SMS_FORMAT enumeration%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
