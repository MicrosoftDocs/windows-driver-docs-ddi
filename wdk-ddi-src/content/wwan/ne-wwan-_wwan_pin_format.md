---
UID: NE:wwan._WWAN_PIN_FORMAT
title: _WWAN_PIN_FORMAT (wwan.h)
description: The WWAN_PIN_FORMAT enumeration lists the different Personal Identification Number (PIN) formats that are supported by the MB device.
old-location: netvista\wwan_pin_format.htm
tech.root: netvista
ms.assetid: ccc3934c-fed4-4f9d-ae2a-d5e96bdb1e46
ms.date: 05/02/2018
keywords: ["WWAN_PIN_FORMAT enumeration"]
ms.keywords: "*PWWAN_PIN_FORMAT, PWWAN_PIN_FORMAT, PWWAN_PIN_FORMAT enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_PIN_FORMAT, WWAN_PIN_FORMAT enumeration [Network Drivers Starting with Windows Vista], WwanPinFormatAlphaNumeric, WwanPinFormatMax, WwanPinFormatNumeric, WwanPinFormatUnknown, WwanRef_f3030aa5-70d9-46d6-85e1-dc112a5889ce.xml, _WWAN_PIN_FORMAT, netvista.wwan_pin_format, wwan/PWWAN_PIN_FORMAT, wwan/WWAN_PIN_FORMAT, wwan/WwanPinFormatAlphaNumeric, wwan/WwanPinFormatMax, wwan/WwanPinFormatNumeric, wwan/WwanPinFormatUnknown"
f1_keywords:
 - "wwan/WWAN_PIN_FORMAT"
 - "WWAN_PIN_FORMAT"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wwan.h
api_name:
- WWAN_PIN_FORMAT
targetos: Windows
req.typenames: WWAN_PIN_FORMAT, *PWWAN_PIN_FORMAT
---

# _WWAN_PIN_FORMAT enumeration


## -description


The WWAN_PIN_FORMAT enumeration lists the different Personal Identification Number (PIN) formats that
  are supported by the MB device.


## -enum-fields




### -field WwanPinFormatUnknown

The format of PIN is not specified.


### -field WwanPinFormatNumeric

The format of the PIN allows only the numerical characters 0 through 9.


### -field WwanPinFormatAlphaNumeric

The format of the PIN allows alphanumeric characters a through z (lowercase), A through Z
     (uppercase), 0 through 9 (numeric), the asterisk symbol (*), and the pound symbol (#).


### -field WwanPinFormatMax

The total number of supported PIN formats.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_pin_desc">WWAN_PIN_DESC</a>
 

 

