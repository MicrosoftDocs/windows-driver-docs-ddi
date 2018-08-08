---
UID: NE:d3d12umddi.D3D12DDI_HEAP_SERIALIZATION_TIER_0041
title: D3D12DDI_HEAP_SERIALIZATION_TIER_0041
author: windows-driver-content
description:
ms.assetid: 6b2f3ca2-ccde-4b2a-9747-65d681bf28b2
ms.author: windowsdriverdev
ms.date:
ms.topic: enum
ms.keywords: D3D12DDI_HEAP_SERIALIZATION_TIER_0041, D3D12DDI_HEAP_SERIALIZATION_TIER_0041,
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: D3D12DDI_HEAP_SERIALIZATION_TIER_0041
topictype:
-	apiref
apitype:
-	HeaderDef
apilocation:
-	d3d12umddi.h
apiname:
-	D3D12DDI_HEAP_SERIALIZATION_TIER_0041
product: 
- Windows
targetos: Windows
---

# D3D12DDI_HEAP_SERIALIZATION_TIER_0041 enumeration

## -description

Defines the heap serialization tier.

## -enum-fields

### -field D3D12DDI_HEAP_SERIALIZATION_TIER_0041_0

Tier level 0 indicates that there is no hardware support for heap serialization. GPU access to a buffer overlapping a texture is may divulge disjoint TBWC metadata representations.

### -field D3D12DDI_HEAP_SERIALIZATION_TIER_0041_1

Tier level 1 indicates that there is hardware support for heap serialization. Seamless Texture BandWidth Compression (TWBC) guarantees that textures are always observable in their parameterized swizzle representations, by overlapping resources. The Driver verifier will ensure resource serialization tier 2 in addition to heap serialization tier 1.

