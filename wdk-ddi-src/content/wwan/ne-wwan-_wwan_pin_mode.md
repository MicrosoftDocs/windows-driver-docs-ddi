---
UID: NE:wwan._WWAN_PIN_MODE
title: _WWAN_PIN_MODE
author: windows-driver-content
description: The WWAN_PIN_MODE enumeration lists the different states of a Personal Identification Number (PIN) type.
old-location: netvista\wwan_pin_mode.htm
old-project: netvista
ms.assetid: 55fa9dd4-370e-4f72-be40-4f14373cee27
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WWAN_PIN_MODE, WWAN_PIN_MODE, *PWWAN_PIN_MODE
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
req.alt-api: WWAN_PIN_MODE
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
req.typenames: WWAN_PIN_MODE, *PWWAN_PIN_MODE
req.product: Windows 10 or later.
---

# _WWAN_PIN_MODE enumeration



## -description
The WWAN_PIN_MODE enumeration lists the different states of a Personal Identification Number (PIN)
  type.



## -syntax

````
typedef enum _WWAN_PIN_MODE { 
  WwanPinModeNotSupported  = 0,
  WwanPinModeEnabled,
  WwanPinModeDisabled,
  WwanPinModeMax
} WWAN_PIN_MODE, *PWWAN_PIN_MODE;
````


## -enum-fields

### -field WwanPinModeNotSupported

The PIN type is not supported.


### -field WwanPinModeEnabled

The PIN type is supported and currently enabled.


### -field WwanPinModeDisabled

The PIN type is supported though currently disabled.


### -field WwanPinModeMax

The total number of supported PIN type states.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\wwan\ns-wwan-_wwan_pin_desc.md">WWAN_PIN_DESC</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_PIN_MODE enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

