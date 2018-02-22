---
UID: NE:wwan._WWAN_SMS_CDMA_ENCODING
title: "_WWAN_SMS_CDMA_ENCODING"
author: windows-driver-content
description: The WWAN_SMS_CDMA_ENCODING enumeration lists the different SMS CDMA encoding formats that are supported by the MB device.
old-location: netvista\wwan_sms_cdma_encoding.htm
old-project: netvista
ms.assetid: 1f632da2-36bb-491e-b445-5c320277a446
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: WwanSmsCdmaEncodingMax, WWAN_SMS_CDMA_ENCODING enumeration [Network Drivers Starting with Windows Vista], *PWWAN_SMS_CDMA_ENCODING, WwanSmsCdmaEncodingUnicode, WwanSmsCdmaEncodingOctet, wwan/WwanSmsCdmaEncodingUnicode, WwanSmsCdmaEncodingShiftJis, PWWAN_SMS_CDMA_ENCODING enumeration pointer [Network Drivers Starting with Windows Vista], WwanSmsCdmaEncodingEpm, WwanSmsCdmaEncodingLatin, _WWAN_SMS_CDMA_ENCODING, WwanSmsCdmaEncoding7BitAscii, WwanSmsCdmaEncodingGsm7Bit, wwan/WwanSmsCdmaEncodingKorean, wwan/WwanSmsCdmaEncodingGsm7Bit, wwan/PWWAN_SMS_CDMA_ENCODING, WWAN_SMS_CDMA_ENCODING, netvista.wwan_sms_cdma_encoding, wwan/WWAN_SMS_CDMA_ENCODING, wwan/WwanSmsCdmaEncodingMax, wwan/WwanSmsCdmaEncodingLatin, WwanRef_a106195c-4a1c-4f95-9c38-91390dadf046.xml, wwan/WwanSmsCdmaEncodingShiftJis, wwan/WwanSmsCdmaEncodingOctet, wwan/WwanSmsCdmaEncodingIa5, WwanSmsCdmaEncodingIa5, wwan/WwanSmsCdmaEncodingEpm, WwanSmsCdmaEncodingKorean, wwan/WwanSmsCdmaEncodingLatinHebrew, PWWAN_SMS_CDMA_ENCODING, wwan/WwanSmsCdmaEncoding7BitAscii, WwanSmsCdmaEncodingLatinHebrew
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wwan.h
apiname:
-	WWAN_SMS_CDMA_ENCODING
product: Windows
targetos: Windows
req.typenames: "*PWWAN_SMS_CDMA_ENCODING, WWAN_SMS_CDMA_ENCODING"
req.product: Windows 10 or later.
---

# _WWAN_SMS_CDMA_ENCODING enumeration


## -description


The WWAN_SMS_CDMA_ENCODING enumeration lists the different SMS CDMA encoding formats that are
  supported by the MB device.


## -syntax


````
typedef enum _WWAN_SMS_CDMA_ENCODING { 
  WwanSmsCdmaEncodingOctet        = 0,
  WwanSmsCdmaEncodingEpm,
  WwanSmsCdmaEncoding7BitAscii,
  WwanSmsCdmaEncodingIa5,
  WwanSmsCdmaEncodingUnicode,
  WwanSmsCdmaEncodingShiftJis,
  WwanSmsCdmaEncodingKorean,
  WwanSmsCdmaEncodingLatinHebrew,
  WwanSmsCdmaEncodingLatin,
  WwanSmsCdmaEncodingGsm7Bit,
  WwanSmsCdmaEncodingMax
} WWAN_SMS_CDMA_ENCODING, *PWWAN_SMS_CDMA_ENCODING;
````


## -enum-fields




### -field WwanSmsCdmaEncodingOctet

The message uses octet encoding.


### -field WwanSmsCdmaEncodingEpm

The message uses EPM encoding.


### -field WwanSmsCdmaEncoding7BitAscii

The message uses 7-bit ASCII encoding. The encoded message is represented in bytes per character.


### -field WwanSmsCdmaEncodingIa5

The message uses IA5 encoding.


### -field WwanSmsCdmaEncodingUnicode

The message uses Unicode encoding.


### -field WwanSmsCdmaEncodingShiftJis

The message uses shifted JIS encoding.


### -field WwanSmsCdmaEncodingKorean

The message uses Korean encoding.


### -field WwanSmsCdmaEncodingLatinHebrew

The message uses Latin Hebrew encoding.


### -field WwanSmsCdmaEncodingLatin

The message uses Latin encoding.


### -field WwanSmsCdmaEncodingGsm7Bit

The message uses 7-bit GSM encoding.


### -field WwanSmsCdmaEncodingMax

The total number of supported SMS CDMA encoding formats.


## -see-also

<a href="..\wwan\ns-wwan-_wwan_sms_send_cdma.md">WWAN_SMS_SEND_CDMA</a>



<a href="..\wwan\ns-wwan-_wwan_sms_cdma_record.md">WWAN_SMS_CDMA_RECORD</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_SMS_CDMA_ENCODING enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

