---
UID: NE:wwan._WWAN_PIN_STATE
title: _WWAN_PIN_STATE (wwan.h)
description: The WWAN_PIN_STATE enumeration describes whether the MB device or Subscriber Identity Module (SIM card) requires the user to enter a Personal Identification Number (PIN) to proceed to the next state.
old-location: netvista\wwan_pin_state.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WWAN_PIN_STATE enumeration"]
ms.keywords: "*PWWAN_PIN_STATE, PWWAN_PIN_STATE, PWWAN_PIN_STATE enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_PIN_STATE, WWAN_PIN_STATE enumeration [Network Drivers Starting with Windows Vista], WwanPinStateEnter, WwanPinStateMax, WwanPinStateNone, WwanRef_6adb4dc1-c989-45b5-a27c-b553c9a5fdd0.xml, _WWAN_PIN_STATE, netvista.wwan_pin_state, wwan/PWWAN_PIN_STATE, wwan/WWAN_PIN_STATE, wwan/WwanPinStateEnter, wwan/WwanPinStateMax, wwan/WwanPinStateNone"
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
req.typenames: WWAN_PIN_STATE, *PWWAN_PIN_STATE
f1_keywords:
 - _WWAN_PIN_STATE
 - wwan/_WWAN_PIN_STATE
 - PWWAN_PIN_STATE
 - wwan/PWWAN_PIN_STATE
 - WWAN_PIN_STATE
 - wwan/WWAN_PIN_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_PIN_STATE
 - PWWAN_PIN_STATE
 - WWAN_PIN_STATE
---

# _WWAN_PIN_STATE enumeration


## -description

The WWAN_PIN_STATE enumeration describes whether the MB device or Subscriber Identity Module (SIM
  card) requires the user to enter a Personal Identification Number (PIN) to proceed to the next
  state.

## -enum-fields

### -field WwanPinStateNone

The device does not require a PIN.

### -field WwanPinStateEnter

The device requires the user to enter a PIN.

### -field WwanPinStateMax

The total number of supported PIN states.

## -see-also

<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_pin_info">WWAN_PIN_INFO</a>

