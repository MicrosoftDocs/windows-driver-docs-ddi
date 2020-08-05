---
UID: NE:wwan._WWAN_CONTEXT_ROAMING_CONTROL
title: _WWAN_CONTEXT_ROAMING_CONTROL (wwan.h)
description: The WWAN_CONTEXT_ROAMING_CONTROL enumeration specifies which roaming conditions apply to a provisioned context in a mobile broadband (MBB) modem.
tech.root: netvista
ms.assetid: e692e8ff-7106-4b58-9046-8a7c98d24e2d
ms.date: 08/22/2018
keywords: ["WWAN_CONTEXT_ROAMING_CONTROL enumeration"]
f1_keywords:
 - "wwan/_WWAN_CONTEXT_ROAMING_CONTROL"
 - "_WWAN_CONTEXT_ROAMING_CONTROL"
ms.keywords: _WWAN_CONTEXT_ROAMING_CONTROL, WWAN_CONTEXT_ROAMING_CONTROL, *PWWAN_CONTEXT_ROAMING_CONTROL, 
req.header: wwan.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: WWAN_CONTEXT_ROAMING_CONTROL, *PWWAN_CONTEXT_ROAMING_CONTROL
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- wwan.h
api_name: 
- _WWAN_CONTEXT_ROAMING_CONTROL
product: 
- Windows
targetos: Windows
ms.custom: RS5
---

# _WWAN_CONTEXT_ROAMING_CONTROL enumeration

## -description

The **WWAN_CONTEXT_ROAMING_CONTROL** enumeration specifies which roaming conditions apply to a provisioned context in a mobile broadband (MBB) modem.

## -enum-fields

### -field WwanContextRoamingControlHomeOnly 

Indicates that this context is allowed to be used only on the home network.

### -field WwanContextRoamingControlPartnerOnly 

Indicates that this context is allowed to be used only on partner roaming networks.

### -field WwanContextRoamingControlNonPartnerOnly 

Indicates that this context is allowed to be used only on non-partner roaming networks.

### -field WwanContextRoamingControlHomeAndPartner 

Indicates that this context is allowed to be used only on both the home network and on partner roaming networks.

### -field WwanContextRoamingControlHomeAndNonPartner 

Indicates that this context is allowed to be used only on both the home network and on non-partner roaming networks.

### -field WwanContextRoamingControlPartnerAndNonPartner 

Indicates that this context is allowed to be used only on both partner and non-partner roaming networks.

### -field WwanContextRoamingControlAllowAll 

Indicates that this context is allowed on all networks.

### -field WwanContextRoamingControlMaximum 

The maximum value for this enumeration.

## -remarks

This enumeration is used in the [**WWAN_CONTEXT_V2**](ns-wwan-_wwan_context_v2.md) and [**WWAN_SET_CONTEXT_V2**](ns-wwan-_wwan_set_context_v2.md) structures.

## -see-also

[**WWAN_CONTEXT_V2**](ns-wwan-_wwan_context_v2.md)

[**WWAN_SET_CONTEXT_V2**](ns-wwan-_wwan_set_context_v2.md)
