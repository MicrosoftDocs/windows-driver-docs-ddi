---
UID: NS:d3dkmthk._D3DKMT_SCATTERBLT
title: D3DKMT_SCATTERBLT (d3dkmthk.h)
description: Learn more about the D3DKMT_SCATTERBLT structure.
ms.date: 07/17/2024
req.header: d3dkmthk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3DKMT_SCATTERBLT
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - _D3DKMT_SCATTERBLT
 - d3dkmthk/_D3DKMT_SCATTERBLT
 - D3DKMT_SCATTERBLT
 - d3dkmthk/D3DKMT_SCATTERBLT
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_SCATTERBLT
 - D3DKMT_SCATTERBLT
dev_langs:
 - c++
---

# D3DKMT_SCATTERBLT structure

## -description

The **D3DKMT_SCATTERBLT** structure is reserved for system use. Don't use it in your driver.

## -struct-fields

### -field hLogicalSurfaceDestination

A handle to the logical surface destination.

### -field hDestinationCompSurfDWM

A handle to the destination computer's surface desktop windows manager (DWM).

### -field DestinationCompositionBindingId

The destination composition binding Id.

### -field SourceRect

The source rectangle.

### -field DestinationOffset

The destination offset.

## -remarks

## -see-also
