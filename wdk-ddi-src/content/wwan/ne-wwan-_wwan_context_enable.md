---
UID: NE:wwan._WWAN_CONTEXT_ENABLE
title: _WWAN_CONTEXT_ENABLE
description: The WWAN_CONTEXT_ENABLE enumeration specifies whether a provisioned context is enabled in a mobile broadband (MBB) modem.
tech.root: netvista
ms.assetid: 130c0816-c402-4e13-9589-abac38c43999
ms.date: 08/22/2018
ms.topic: enum
ms.keywords: _WWAN_CONTEXT_ENABLE, WWAN_CONTEXT_ENABLE, *PWWAN_CONTEXT_ENABLE, 
req.header: wwan.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: WWAN_CONTEXT_ENABLE, *PWWAN_CONTEXT_ENABLE
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	wwan.h
api_name: 
-	_WWAN_CONTEXT_ENABLE
product: 
- Windows
targetos: Windows
ms.custom: RS5
---

# _WWAN_CONTEXT_ENABLE enumeration

## -description

The **WWAN_CONTEXT_ENABLE** enumeration specifies whether a provisioned context is enabled in a mobile broadband (MBB) modem.

## -enum-fields

### -field WwanContextDisabled 

The context is disabled.

### -field WwanContextEnabled 

The context is enabled.

### -field WwanContextEnableMaximum 

The maximum value for this enumeration.

## -remarks

This enumeration is used in the [**WWAN_CONTEXT_V2**](ns-wwan-_wwan_context_v2.md) and [**WWAN_SET_CONTEXT_V2**](ns-wwan-_wwan_set_context_v2.md) structures.

## -see-also

[**WWAN_CONTEXT_V2**](ns-wwan-_wwan_context_v2.md)

[**WWAN_SET_CONTEXT_V2**](ns-wwan-_wwan_set_context_v2.md)
