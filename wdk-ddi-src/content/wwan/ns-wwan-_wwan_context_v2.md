---
UID: NS:wwan._WWAN_CONTEXT_V2
title: _WWAN_CONTEXT_V2 (wwan.h)
description: The WWAN_CONTEXT_V2 structure represents a provisioned context that is supported by a mobile broadband (MBB) device. This structure extends the existing WWAN_CONTEXT structure. 
tech.root: netvista
ms.assetid: 8f62c242-bfae-45f3-8772-f64b61fabc33
ms.date: 08/22/2018
ms.topic: struct
ms.keywords: _WWAN_CONTEXT_V2, WWAN_CONTEXT_V2, *PWWAN_CONTEXT_V2, 
req.header: wwan.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: WWAN_CONTEXT_V2, *PWWAN_CONTEXT_V2
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	wwan.h
api_name: 
-	_WWAN_CONTEXT_V2
product: 
- Windows
targetos: Windows
ms.custom: RS5
---

# _WWAN_CONTEXT_V2 structure

## -description

The **WWAN_CONTEXT_V2** structure represents a provisioned context that is supported by a mobile broadband (MBB) device. This structure extends the existing [**WWAN_CONTEXT**](ns-wwan-_wwan_context.md) structure.

## -struct-fields

### -field basicInfo

A [**WWAN_CONTEXT**](ns-wwan-_wwan_context.md) structure that represents the basic information for this provisioned context.
 
### -field IPType

A [**WWAN_IP_TYPE**](ne-wwan-_wwan_ip_type.md) value that specifies the supported IP types for this provisioned context.
 
### -field Enable

A [**WWAN_CONTEXT_ENABLE**](ne-wwan-_wwan_context_enable.md) value that specifies whether the context is enabled or disabled in the modem.
 
### -field Roaming

A [**WWAN_CONTEXT_ROAMING_CONTROL**](ne-wwan-_wwan_context_roaming_control.md) value that specifies which roaming condition applies to this context.
 
### -field MediaType

A [**WWAN_CONTEXT_MEDIA_TYPE**](ne-wwan-_wwan_context_media_type.md) value that specifies the supported media types for this provisioned context.
 
### -field Source

A [**WWAN_CONFIGURATION_SOURCE**](ne-wwan-_wwan_configuration_source.md) value that specifies the creation source of the context.
 
### -field Reserved
 
Reserved for system use. Miniport drivers should not read or write to this value.

## -remarks

**WWAN_CONTEXT_V2** is used as a response to Query or Set requests, unlike [**WWAN_SET_CONTEXT_V2**](ns-wwan-_wwan_set_context_v2.md) which is used for Set requests.

## -see-also

[**WWAN_CONTEXT**](ns-wwan-_wwan_context.md)

[**WWAN_IP_TYPE**](ne-wwan-_wwan_ip_type.md)

[**WWAN_CONTEXT_ENABLE**](ne-wwan-_wwan_context_enable.md)

[**WWAN_CONTEXT_ROAMING_CONTROL**](ne-wwan-_wwan_context_roaming_control.md)

[**WWAN_CONTEXT_MEDIA_TYPE**](ne-wwan-_wwan_context_media_type.md)

[**WWAN_CONFIGURATION_SOURCE**](ne-wwan-_wwan_configuration_source.md)

[**WWAN_SET_CONTEXT_V2**](ns-wwan-_wwan_set_context_v2.md)
