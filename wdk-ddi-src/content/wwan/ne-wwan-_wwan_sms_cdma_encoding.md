---
UID: NE:wwan._WWAN_SMS_CDMA_ENCODING
title: _WWAN_SMS_CDMA_ENCODING (wwan.h)
description: The WWAN_SMS_CDMA_ENCODING enumeration lists the different SMS CDMA encoding formats that are supported by the MB device.
old-location: netvista\wwan_sms_cdma_encoding.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WWAN_SMS_CDMA_ENCODING enumeration"]
ms.keywords: "*PWWAN_SMS_CDMA_ENCODING, PWWAN_SMS_CDMA_ENCODING, PWWAN_SMS_CDMA_ENCODING enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_SMS_CDMA_ENCODING, WWAN_SMS_CDMA_ENCODING enumeration [Network Drivers Starting with Windows Vista], WwanRef_a106195c-4a1c-4f95-9c38-91390dadf046.xml, WwanSmsCdmaEncoding7BitAscii, WwanSmsCdmaEncodingEpm, WwanSmsCdmaEncodingGsm7Bit, WwanSmsCdmaEncodingIa5, WwanSmsCdmaEncodingKorean, WwanSmsCdmaEncodingLatin, WwanSmsCdmaEncodingLatinHebrew, WwanSmsCdmaEncodingMax, WwanSmsCdmaEncodingOctet, WwanSmsCdmaEncodingShiftJis, WwanSmsCdmaEncodingUnicode, _WWAN_SMS_CDMA_ENCODING, netvista.wwan_sms_cdma_encoding, wwan/PWWAN_SMS_CDMA_ENCODING, wwan/WWAN_SMS_CDMA_ENCODING, wwan/WwanSmsCdmaEncoding7BitAscii, wwan/WwanSmsCdmaEncodingEpm, wwan/WwanSmsCdmaEncodingGsm7Bit, wwan/WwanSmsCdmaEncodingIa5, wwan/WwanSmsCdmaEncodingKorean, wwan/WwanSmsCdmaEncodingLatin, wwan/WwanSmsCdmaEncodingLatinHebrew, wwan/WwanSmsCdmaEncodingMax, wwan/WwanSmsCdmaEncodingOctet, wwan/WwanSmsCdmaEncodingShiftJis, wwan/WwanSmsCdmaEncodingUnicode"
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
targetos: Windows
req.typenames: WWAN_SMS_CDMA_ENCODING, *PWWAN_SMS_CDMA_ENCODING
f1_keywords:
 - _WWAN_SMS_CDMA_ENCODING
 - wwan/_WWAN_SMS_CDMA_ENCODING
 - PWWAN_SMS_CDMA_ENCODING
 - wwan/PWWAN_SMS_CDMA_ENCODING
 - WWAN_SMS_CDMA_ENCODING
 - wwan/WWAN_SMS_CDMA_ENCODING
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_SMS_CDMA_ENCODING
 - PWWAN_SMS_CDMA_ENCODING
 - WWAN_SMS_CDMA_ENCODING
---

# _WWAN_SMS_CDMA_ENCODING enumeration


## -description

The WWAN_SMS_CDMA_ENCODING enumeration lists the different SMS CDMA encoding formats that are
  supported by the MB device.

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

<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_sms_cdma_record">WWAN_SMS_CDMA_RECORD</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_sms_send_cdma">WWAN_SMS_SEND_CDMA</a>

