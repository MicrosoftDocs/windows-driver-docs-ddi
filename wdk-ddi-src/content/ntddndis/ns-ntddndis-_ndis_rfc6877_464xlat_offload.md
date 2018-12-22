---
UID: NS:ntddndis._NDIS_RFC6877_464XLAT_OFFLOAD
title: _NDIS_RFC6877_464XLAT_OFFLOAD
description: The NDIS_RFC6877_464XLAT_OFFLOAD structure contains 464XLAT hardware offload information.
tech.root: netvista
ms.assetid: d94bee25-3b7f-43d1-8319-abf41e6e4b3c
ms.date: 05/22/2018
ms.topic: struct
ms.keywords: _NDIS_RFC6877_464XLAT_OFFLOAD, NDIS_RFC6877_464XLAT_OFFLOAD, *PNDIS_RFC6877_464XLAT_OFFLOAD, 
req.header: ntddndis.h
req.include-header: ndis.h
req.target-type:
req.target-min-winverclnt: NDIS 6.70
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: NDIS_RFC6877_464XLAT_OFFLOAD, *PNDIS_RFC6877_464XLAT_OFFLOAD
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	ntddndis.h
api_name: 
-	_NDIS_RFC6877_464XLAT_OFFLOAD
product:
-	Windows
targetos: Windows
ms.custom: RS5
---

# _NDIS_RFC6877_464XLAT_OFFLOAD structure

## -description

The **NDIS_RFC6877_464XLAT_OFFLOAD** structure contains 464XLAT hardware offload information.

## -struct-fields

### -field XlatOffload

An [**NDIS_RFC6877_464XLAT_OFFLOAD_OPTIONS**](ne-ntddndis-_ndis_rfc6877_464xlat_offload_options.md) value that describes a miniport driver's 464XLAT hardware offload capabilities.
 
### -field Flags
 
Reserved for system use. This member is always zero (0).

## -remarks

## -see-also

[**NDIS_OFFLOAD**](ns-ntddndis-_ndis_offload.md)
