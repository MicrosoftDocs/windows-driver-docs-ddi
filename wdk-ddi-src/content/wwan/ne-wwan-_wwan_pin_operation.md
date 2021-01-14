---
UID: NE:wwan._WWAN_PIN_OPERATION
title: _WWAN_PIN_OPERATION (wwan.h)
description: The WWAN_PIN_OPERATION enumeration lists the different Personal Identification Number (PIN) operations that are supported by the MB device.
old-location: netvista\wwan_pin_operation.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WWAN_PIN_OPERATION enumeration"]
ms.keywords: "*PWWAN_PIN_OPERATION, PWWAN_PIN_OPERATION, PWWAN_PIN_OPERATION enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_PIN_OPERATION, WWAN_PIN_OPERATION enumeration [Network Drivers Starting with Windows Vista], WwanPinOperationChange, WwanPinOperationDisable, WwanPinOperationEnable, WwanPinOperationEnter, WwanPinOperationMax, WwanRef_06404d11-22d3-4b07-9c6f-60771ecfc154.xml, _WWAN_PIN_OPERATION, netvista.wwan_pin_operation, wwan/PWWAN_PIN_OPERATION, wwan/WWAN_PIN_OPERATION, wwan/WwanPinOperationChange, wwan/WwanPinOperationDisable, wwan/WwanPinOperationEnable, wwan/WwanPinOperationEnter, wwan/WwanPinOperationMax"
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
req.typenames: WWAN_PIN_OPERATION, *PWWAN_PIN_OPERATION
f1_keywords:
 - _WWAN_PIN_OPERATION
 - wwan/_WWAN_PIN_OPERATION
 - PWWAN_PIN_OPERATION
 - wwan/PWWAN_PIN_OPERATION
 - WWAN_PIN_OPERATION
 - wwan/WWAN_PIN_OPERATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_PIN_OPERATION
 - PWWAN_PIN_OPERATION
 - WWAN_PIN_OPERATION
---

# _WWAN_PIN_OPERATION enumeration


## -description

The WWAN_PIN_OPERATION enumeration lists the different Personal Identification Number (PIN)
  operations that are supported by the MB device.

## -enum-fields

### -field WwanPinOperationEnter

Enter the specified PIN into the device.

### -field WwanPinOperationEnable

Enable the specified PIN.

### -field WwanPinOperationDisable

Disable the specified PIN.

### -field WwanPinOperationChange

Change the specified PIN.

### -field WwanPinOperationMax

The total number of supported PIN operations.

## -remarks

If a PIN disable operation for a given PIN type is tried when that PIN type is locked, miniport
    drivers can either fail the request with WWAN_STATUS_PIN_REQUIRED or they can successfully complete the
    request. If miniport drivers complete the request successfully, the disable operation should also unlock
    the PIN.

## -see-also

<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_pin_action">WWAN_PIN_ACTION</a>

