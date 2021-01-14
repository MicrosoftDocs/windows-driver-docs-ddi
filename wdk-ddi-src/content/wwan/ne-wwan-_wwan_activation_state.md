---
UID: NE:wwan._WWAN_ACTIVATION_STATE
title: _WWAN_ACTIVATION_STATE (wwan.h)
description: The WWAN_ACTIVATION_STATE enumeration lists the different Packet Data Protocol (PDP) context activation states that are supported by the MB device.
old-location: netvista\wwan_activation_state.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WWAN_ACTIVATION_STATE enumeration"]
ms.keywords: "*PWWAN_ACTIVATION_STATE, PWWAN_ACTIVATION_STATE, PWWAN_ACTIVATION_STATE enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_ACTIVATION_STATE, WWAN_ACTIVATION_STATE enumeration [Network Drivers Starting with Windows Vista], WwanActivationStateActivated, WwanActivationStateActivating, WwanActivationStateDeactivated, WwanActivationStateDeactivating, WwanActivationStateMax, WwanActivationStateUnknown, WwanRef_d1e0cf59-316c-45a2-8ae3-231c30cae091.xml, _WWAN_ACTIVATION_STATE, netvista.wwan_activation_state, wwan/PWWAN_ACTIVATION_STATE, wwan/WWAN_ACTIVATION_STATE, wwan/WwanActivationStateActivated, wwan/WwanActivationStateActivating, wwan/WwanActivationStateDeactivated, wwan/WwanActivationStateDeactivating, wwan/WwanActivationStateMax, wwan/WwanActivationStateUnknown"
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
req.typenames: WWAN_ACTIVATION_STATE, *PWWAN_ACTIVATION_STATE
f1_keywords:
 - _WWAN_ACTIVATION_STATE
 - wwan/_WWAN_ACTIVATION_STATE
 - PWWAN_ACTIVATION_STATE
 - wwan/PWWAN_ACTIVATION_STATE
 - WWAN_ACTIVATION_STATE
 - wwan/WWAN_ACTIVATION_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_ACTIVATION_STATE
 - PWWAN_ACTIVATION_STATE
 - WWAN_ACTIVATION_STATE
---

# _WWAN_ACTIVATION_STATE enumeration


## -description

The WWAN_ACTIVATION_STATE enumeration lists the different Packet Data Protocol (PDP) context
  activation states that are supported by the MB device.

## -enum-fields

### -field WwanActivationStateUnknown

The activation state is unknown.

### -field WwanActivationStateActivated

The packet context is activated.

### -field WwanActivationStateActivating

The packet context is currently in the process of getting activated.

### -field WwanActivationStateDeactivated

The packet context is not activated.

### -field WwanActivationStateDeactivating

The packet context is currently in the process of getting deactivated.

### -field WwanActivationStateMax

The total number of PDP activation states.

## -remarks

Miniport drivers use the 
    <b>WwanActivationStateActivating</b> and 
    <b>WwanActivationStateDeactivating</b> transient states when responding to 
    <i>query</i> requests. Miniport driver should not return these states when processing 
    <i>set</i> requests. Miniport drivers must only send 
    <i>set</i> indications after they have successfully activated or deactivated a PDP context, and not
    immediately after receiving the request.

## -see-also

<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_set_context_state">WWAN_SET_CONTEXT_STATE</a>

