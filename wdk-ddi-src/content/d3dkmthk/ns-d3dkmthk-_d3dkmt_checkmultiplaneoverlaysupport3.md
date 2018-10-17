---
UID: NS:d3dkmthk._D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3
title: _D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3
author: windows-driver-content
description: Check for multiplane overlay support.
ms.assetid: 864fba9e-5cdf-440f-8177-33beed94030e
ms.date: 
ms.topic: struct
ms.keywords: _D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3, D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3, 
req.header: d3dkmthk.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3dkmthk.h
api_name: 
-	_D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3
product:
-	Windows
targetos: Windows
---

# _D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3 structure

## -description

Check for multiplane overlay support.

## -struct-fields

### -field hAdapter

A handle to the graphics adapter.

### -field hDevice

A handle to the device.

### -field PlaneCount

The number of resources to pin.

### -field ppOverlayPlanes

Array of pointers to overlay planes.

### -field PostCompositionCount

The number of resources to pin.

### -field ppPostComposition

Array of pointers to overlay planes.

### -field Supported

Indicates support.

### -field ReturnInfo
 
The return info.

## -remarks

## -see-also
