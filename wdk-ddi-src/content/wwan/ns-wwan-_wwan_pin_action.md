---
UID: NS:wwan._WWAN_PIN_ACTION
title: _WWAN_PIN_ACTION (wwan.h)
description: The WWAN_PIN_ACTION structure represents actions to perform with a Personal Identification Number (PIN).
old-location: netvista\wwan_pin_action.htm
tech.root: netvista
ms.assetid: 4edd0bc1-cd50-460b-92e1-7b2440ae3861
ms.date: 05/02/2018
keywords: ["_WWAN_PIN_ACTION structure"]
ms.keywords: "*PWWAN_PIN_ACTION, PWWAN_PIN_ACTION, PWWAN_PIN_ACTION structure pointer [Network Drivers Starting with Windows Vista], WWAN_PIN_ACTION, WWAN_PIN_ACTION structure [Network Drivers Starting with Windows Vista], WwanRef_831c483c-8839-43a4-870d-f63ea3f78b61.xml, _WWAN_PIN_ACTION, netvista.wwan_pin_action, wwan/PWWAN_PIN_ACTION, wwan/WWAN_PIN_ACTION"
f1_keywords:
 - "wwan/WWAN_PIN_ACTION"
 - "WWAN_PIN_ACTION"
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
- WWAN_PIN_ACTION
product:
- Windows
targetos: Windows
req.typenames: WWAN_PIN_ACTION, *PWWAN_PIN_ACTION
---

# _WWAN_PIN_ACTION structure


## -description


The WWAN_PIN_ACTION structure represents actions to perform with a Personal Identification Number
  (PIN).


## -struct-fields




### -field PinType

The type of the PIN on which to perform the action.


### -field PinOperation

The action to perform with the PIN. For more information, see [WWAN_PIN_OPERATION](ne-wwan-_wwan_pin_operation.md).


### -field Pin

A NULL-terminated string that represents the PIN value to perform the action with, or the PIN
     value required to enable/disable PIN settings. This member is a numeric value and applies for all values of 
     <b>PinOperation</b> .


### -field NewPin

A NULL-terminated string that represents the new PIN value to set when 
     <b>PinOperation</b> is 
     <b>WwanPinOperationChange</b> or 
     <b>WwanPinOperationEnter</b>, for 
     <b>PinType</b><b>WwanPinTypePuk1</b> or 
     <b>WwanPinTypePuk2</b>. This member is a numeric value.


### -field RequestPinOperationPrompt

A BOOLEAN value that indicates whether to display a prompt to request the PIN operation.


## -remarks



When 
    <b>PinType</b> is 
    <b>WwanPinTypePuk1</b> or 
    <b>WwanPinTypePuk2</b>, 
    <b>Pin</b> represents the corresponding PUK key.

When 
    <b>PinType</b> is 
    <b>WwanPinTypePuk1</b> or 
    <b>WwanPinTypePuk2, WwanPinOperationEnter</b> is the only supported value for 
    <b>PinOperation</b> .




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndiswwan/ns-ndiswwan-_ndis_wwan_set_pin">NDIS_WWAN_SET_PIN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ne-wwan-_wwan_pin_operation">WWAN_PIN_OPERATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ne-wwan-_wwan_pin_type">WWAN_PIN_TYPE</a>
 

 

