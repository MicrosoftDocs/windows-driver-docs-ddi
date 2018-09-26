---
UID: NE:d3dumddi._D3DDDI_COMPOSERECTSOP
title: _D3DDDI_COMPOSERECTSOP
author: windows-driver-content
description: Describes the ways in which to compose rectangle areas.
ms.assetid: 8eed3d12-86ec-4184-8087-eb5490096437
ms.author: windowsdriverdev
ms.date: 
ms.topic: enum
ms.keywords: _D3DDDI_COMPOSERECTSOP, D3DDDI_COMPOSERECTSOP, 
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3dumddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: D3DDDI_COMPOSERECTSOP
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3dumddi.h
api_name: 
-	_D3DDDI_COMPOSERECTSOP
product:
-	Windows
targetos: Windows
---

# _D3DDDI_COMPOSERECTSOP enumeration

## -description

Describes the ways in which to compose rectangle areas.

## -enum-fields

### -field D3DDDICOMPOSERECTS_COPY

Copy.

### -field D3DDDICOMPOSERECTS_OR

Use an OR.

### -field D3DDDICOMPOSERECTS_AND

Use an AND.

### -field D3DDDICOMPOSERECTS_NEG

Use NEG.

### -field D3DDDICOMPOSERECTS_FORCE_UINT 

Forces this enumeration to compile to 32 bits in size. Without this value, some compilers would allow this enumeration to compile to a size other than 32 bits. You should not use this value.

## -remarks

## -see-also