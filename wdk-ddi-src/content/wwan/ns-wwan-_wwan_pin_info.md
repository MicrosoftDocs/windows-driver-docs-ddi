---
UID: NS:wwan._WWAN_PIN_INFO
title: _WWAN_PIN_INFO (wwan.h)
description: The WWAN_PIN_INFO structure represents PIN type and PIN-entry state of Personal Identification Number (PIN) information required by the MB device.
old-location: netvista\wwan_pin_info.htm
tech.root: netvista
ms.assetid: 0711645f-791b-4643-95c3-604ecce2a5ed
ms.date: 05/02/2018
ms.keywords: "*PWWAN_PIN_INFO, PWWAN_PIN_INFO, PWWAN_PIN_INFO structure pointer [Network Drivers Starting with Windows Vista], WWAN_PIN_INFO, WWAN_PIN_INFO structure [Network Drivers Starting with Windows Vista], WwanRef_aae7d248-25b1-465b-9314-66a16aca4993.xml, _WWAN_PIN_INFO, netvista.wwan_pin_info, wwan/PWWAN_PIN_INFO, wwan/WWAN_PIN_INFO"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wwan.h
api_name:
- WWAN_PIN_INFO
product:
- Windows
targetos: Windows
req.typenames: WWAN_PIN_INFO, *PWWAN_PIN_INFO
---

# _WWAN_PIN_INFO structure


## -description


The WWAN_PIN_INFO structure represents PIN type and PIN-entry state of Personal Identification Number
  (PIN) information required by the MB device.


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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndiswwan/ns-ndiswwan-_ndis_wwan_pin_info">NDIS_WWAN_PIN_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ne-wwan-_wwan_pin_state">WWAN_PIN_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ne-wwan-_wwan_pin_type">WWAN_PIN_TYPE</a>
 

 

