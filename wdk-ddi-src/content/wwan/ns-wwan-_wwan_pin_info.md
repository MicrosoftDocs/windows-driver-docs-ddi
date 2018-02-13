---
UID: NS:wwan._WWAN_PIN_INFO
title: "_WWAN_PIN_INFO"
author: windows-driver-content
description: The WWAN_PIN_INFO structure represents PIN type and PIN-entry state of Personal Identification Number (PIN) information required by the MB device.
old-location: netvista\wwan_pin_info.htm
old-project: netvista
ms.assetid: 0711645f-791b-4643-95c3-604ecce2a5ed
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*PWWAN_PIN_INFO, PWWAN_PIN_INFO, PWWAN_PIN_INFO structure pointer [Network Drivers Starting with Windows Vista], _WWAN_PIN_INFO, WWAN_PIN_INFO structure [Network Drivers Starting with Windows Vista], wwan/PWWAN_PIN_INFO, netvista.wwan_pin_info, WwanRef_aae7d248-25b1-465b-9314-66a16aca4993.xml, WWAN_PIN_INFO, wwan/WWAN_PIN_INFO"
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
-	WWAN_PIN_INFO
product: Windows
targetos: Windows
req.typenames: WWAN_PIN_INFO, *PWWAN_PIN_INFO
req.product: Windows 10 or later.
---

# _WWAN_PIN_INFO structure


## -description


The WWAN_PIN_INFO structure represents PIN type and PIN-entry state of Personal Identification Number
  (PIN) information required by the MB device.


## -syntax


````
typedef struct _WWAN_PIN_INFO {
  WWAN_PIN_TYPE  PinType;
  WWAN_PIN_STATE PinState;
  ULONG          AttemptsRemaining;
} WWAN_PIN_INFO, *PWWAN_PIN_INFO;
````


## -struct-fields




### -field PinType

The type of PIN required to unlock the information stored on the device.


### -field PinState

The state of PIN-entry required to unlock the device.
     

This value indicates whether the device requires a PIN to be entered or not.


### -field AttemptsRemaining

The number of attempts that remain for any pin-related operations such as enter, enable, disable,
     and change.


## -see-also

<a href="..\wwan\ne-wwan-_wwan_pin_type.md">WWAN_PIN_TYPE</a>



<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_pin_info.md">NDIS_WWAN_PIN_INFO</a>



<a href="..\wwan\ne-wwan-_wwan_pin_state.md">WWAN_PIN_STATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_PIN_INFO structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

