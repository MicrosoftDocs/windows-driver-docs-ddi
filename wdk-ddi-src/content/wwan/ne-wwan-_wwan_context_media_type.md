---
UID: NE:wwan._WWAN_CONTEXT_MEDIA_TYPE
title: _WWAN_CONTEXT_MEDIA_TYPE (wwan.h)
description: The WWAN_CONTEXT_MEDIA_TYPE enumeration specifies the type of media supported for a provisioned context in a mobile broadband (MBB) modem.
tech.root: netvista
ms.assetid: 1ec0496c-61a8-4148-9a13-6964f68555cb
ms.date: 08/22/2018
ms.topic: enum
ms.keywords: _WWAN_CONTEXT_MEDIA_TYPE, WWAN_CONTEXT_MEDIA_TYPE, *PWWAN_CONTEXT_MEDIA_TYPE, 
req.header: wwan.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: WWAN_CONTEXT_MEDIA_TYPE, *PWWAN_CONTEXT_MEDIA_TYPE
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	wwan.h
api_name: 
-	_WWAN_CONTEXT_MEDIA_TYPE
product: 
- Windows
targetos: Windows
ms.custom: RS5
---

# _WWAN_CONTEXT_MEDIA_TYPE enumeration

## -description

The **WWAN_CONTEXT_MEDIA_TYPE** enumeration specifies the type of media supported for a provisioned context in a mobile broadband (MBB) modem.

## -enum-fields

### -field WwanContextMediaTypeCellularOnly 

The context's media type is cellular only.

### -field WwanContextMediaTypeWifiOnly 

The context's media type is Wi-Fi only.

### -field WwanContextMediaTypeAll 

The context's media type is both cellular and Wi-Fi.

### -field WwanContextMediaTypeMaximum 

The maximum value for this enumeration.

## -remarks

This enumeration is used in the [**WWAN_CONTEXT_V2**](ns-wwan-_wwan_context_v2.md) and [**WWAN_SET_CONTEXT_V2**](ns-wwan-_wwan_set_context_v2.md) structures.

## -see-also

[**WWAN_CONTEXT_V2**](ns-wwan-_wwan_context_v2.md)

[**WWAN_SET_CONTEXT_V2**](ns-wwan-_wwan_set_context_v2.md)
