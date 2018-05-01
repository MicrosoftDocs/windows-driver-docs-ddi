---
UID: NE:wwan._WWAN_PIN_MODE
title: "_WWAN_PIN_MODE"
author: windows-driver-content
description: The WWAN_PIN_MODE enumeration lists the different states of a Personal Identification Number (PIN) type.
old-location: netvista\wwan_pin_mode.htm
old-project: netvista
ms.assetid: 55fa9dd4-370e-4f72-be40-4f14373cee27
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PWWAN_PIN_MODE, PWWAN_PIN_MODE, PWWAN_PIN_MODE enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_PIN_MODE, WWAN_PIN_MODE enumeration [Network Drivers Starting with Windows Vista], WwanPinModeDisabled, WwanPinModeEnabled, WwanPinModeMax, WwanPinModeNotSupported, WwanRef_43194a1d-461a-4793-bb0b-40354466610c.xml, _WWAN_PIN_MODE, netvista.wwan_pin_mode, wwan/PWWAN_PIN_MODE, wwan/WWAN_PIN_MODE, wwan/WwanPinModeDisabled, wwan/WwanPinModeEnabled, wwan/WwanPinModeMax, wwan/WwanPinModeNotSupported"
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wwan.h
api_name:
-	WWAN_PIN_MODE
product: Windows
targetos: Windows
req.typenames: WWAN_PIN_MODE, *PWWAN_PIN_MODE
---

# _WWAN_PIN_MODE enumeration


## -description


The WWAN_PIN_MODE enumeration lists the different states of a Personal Identification Number (PIN)
  type.


## -enum-fields




### -field WwanPinModeNotSupported

The PIN type is not supported.


### -field WwanPinModeEnabled

The PIN type is supported and currently enabled.


### -field WwanPinModeDisabled

The PIN type is supported though currently disabled.


### -field WwanPinModeMax

The total number of supported PIN type states.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff571214">WWAN_PIN_DESC</a>
 

 

