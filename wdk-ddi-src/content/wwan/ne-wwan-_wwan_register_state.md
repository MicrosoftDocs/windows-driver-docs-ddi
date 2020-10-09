---
UID: NE:wwan._WWAN_REGISTER_STATE
title: _WWAN_REGISTER_STATE (wwan.h)
description: The WWAN_REGISTER_STATE enumeration lists the different provider network registration states that are supported by the MB device.
old-location: netvista\wwan_register_state.htm
tech.root: netvista
ms.assetid: fba4e60e-c247-4466-9b0f-c8e7ffa594d2
ms.date: 05/02/2018
keywords: ["WWAN_REGISTER_STATE enumeration"]
ms.keywords: "*PWWAN_REGISTER_STATE, PWWAN_REGISTER_STATE, PWWAN_REGISTER_STATE enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_REGISTER_STATE, WWAN_REGISTER_STATE enumeration [Network Drivers Starting with Windows Vista], WwanRef_927c04e0-b022-4d93-8052-696b5e9da51f.xml, WwanRegisterStateDenied, WwanRegisterStateDeregistered, WwanRegisterStateHome, WwanRegisterStateMax, WwanRegisterStatePartner, WwanRegisterStateRoaming, WwanRegisterStateSearching, WwanRegisterStateUnknown, _WWAN_REGISTER_STATE, netvista.wwan_register_state, wwan/PWWAN_REGISTER_STATE, wwan/WWAN_REGISTER_STATE, wwan/WwanRegisterStateDenied, wwan/WwanRegisterStateDeregistered, wwan/WwanRegisterStateHome, wwan/WwanRegisterStateMax, wwan/WwanRegisterStatePartner, wwan/WwanRegisterStateRoaming, wwan/WwanRegisterStateSearching, wwan/WwanRegisterStateUnknown"
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
req.typenames: WWAN_REGISTER_STATE, *PWWAN_REGISTER_STATE
f1_keywords:
 - _WWAN_REGISTER_STATE
 - wwan/_WWAN_REGISTER_STATE
 - PWWAN_REGISTER_STATE
 - wwan/PWWAN_REGISTER_STATE
 - WWAN_REGISTER_STATE
 - wwan/WWAN_REGISTER_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - WWAN_REGISTER_STATE
---

# _WWAN_REGISTER_STATE enumeration


## -description

The WWAN_REGISTER_STATE enumeration lists the different provider network registration states that are
  supported by the MB device.

## -enum-fields

### -field WwanRegisterStateUnknown

The current registration state is unknown. The miniport driver may specify this state on a failure
     to set an appropriate 
     <i>WwanRegisterActionXxx</i>.

### -field WwanRegisterStateDeregistered

The device is not registered and is not searching for network providers.

### -field WwanRegisterStateSearching

The device is searching for a network provider.

### -field WwanRegisterStateHome

The device is using the home network provider.

### -field WwanRegisterStateRoaming

The device is using a network provider that supports roaming.

### -field WwanRegisterStatePartner

The device is using a roaming network partner.

### -field WwanRegisterStateDenied

Registration of the device on visible networks has been denied. However, emergency voice calls may
     still be made. This value applies only to voice connections, and not to data connections.

### -field WwanRegisterStateMax

The total number of supported registration states.

## -remarks

The current registration state is typically reflected in the device's user interface.

The 
    <b>WwanRegisterStatePartner</b> value indicates that the device is roaming on a preferred partner network,
    whereas 
    <b>WwanRegisterStateRoaming</b> value indicates that the device is just roaming. If the partner
    characterization of the roaming state is not available, the miniport driver should report 
    <b>WwanRegisterStateRoaming</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_registration_state">WWAN_REGISTRATION_STATE</a>