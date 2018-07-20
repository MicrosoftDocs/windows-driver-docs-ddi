---
UID: NS:wwan._WWAN_PIN_DESC
title: "_WWAN_PIN_DESC"
author: windows-driver-content
description: The WWAN_PIN_DESC structure represents the description or current status for a Personal Identification Number (PIN).
old-location: netvista\wwan_pin_desc.htm
tech.root: netvista
ms.assetid: a88f56eb-b527-4c7c-8f59-650dd10c671e
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: "*PWWAN_PIN_DESC, PWWAN_PIN_DESC, PWWAN_PIN_DESC structure pointer [Network Drivers Starting with Windows Vista], WWAN_PIN_DESC, WWAN_PIN_DESC structure [Network Drivers Starting with Windows Vista], WwanRef_a0c1c3f2-0fcd-465f-bab6-5fa4887159b8.xml, _WWAN_PIN_DESC, netvista.wwan_pin_desc, wwan/PWWAN_PIN_DESC, wwan/WWAN_PIN_DESC"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wwan.h
api_name:
-	WWAN_PIN_DESC
product:
- Windows
targetos: Windows
req.typenames: WWAN_PIN_DESC, *PWWAN_PIN_DESC
---

# _WWAN_PIN_DESC structure


## -description


The WWAN_PIN_DESC structure represents the description or current status for a Personal
  Identification Number (PIN).


## -struct-fields




### -field PinMode

The current status of the PIN.


### -field PinFormat

The format of the PIN. This member is ignored if the 
     <b>PinMode</b> is 
     <b>WwanPinModeNotSupported</b>.


### -field PinLengthMin

The minimum number of characters in the PIN. Miniport drivers should not specify a value that is
     greater than WWAN_PIN_LEN (12). Miniport drivers should specify WWAN_PIN_LENGTH_UNKNOWN, if the PIN
     length is not available.


### -field PinLengthMax

The maximum number of characters in the PIN. Miniport drivers should not specify a value that is
     greater than WWAN_PIN_LEN (12). Miniport drivers should specify WWAN_PIN_LENGTH_UNKNOWN, if the PIN
     length is not available.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff571215">WWAN_PIN_FORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571217">WWAN_PIN_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571218">WWAN_PIN_MODE</a>
 

 

