---
UID: NS:d3dkmthk._D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2
title: _D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2
author: windows-driver-content
description: Check for multiplane overlay support.
ms.assetid: be3459f5-1d74-46d5-b8a6-b8709fd189e4
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2, D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2, 
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
req.typenames: D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3dkmthk.h
api_name: 
-	_D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2
product:
-	Windows
targetos: Windows
---

# _D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2 structure

## -description

Check for multiplane overlay support.

## -struct-fields

### -field hAdapter

A handle to the graphics adapter.

### -field hDevice

A handle to the device.

### -field PlaneCount

The number of resources to pin.

### -field pOverlayPlanes

Array of pointers to overlay planes.

### -field Supported

Indicates support.

### -field ReturnInfo
 
The return info.

## -remarks

## -see-also
