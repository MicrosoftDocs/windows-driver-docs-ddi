---
UID: NS:d3dkmthk._D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT
title: D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT (d3dkmthk.h)
description: Learn more about the D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT structure.
ms.date: 10/04/2023
keywords: ["D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT structure"]
ms.keywords: _D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT, D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT,
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
req.typenames: D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - _D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT
 - d3dkmthk/_D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT
 - D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT
 - d3dkmthk/D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT
 - D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT
dev_langs:
 - c++
---

# D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT structure

This structure has been replaced by [**D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE3**](ns-d3dkmthk-_d3dkmt_check_multiplane_overlay_plane3.md).

## -description

Check for multiplane overlay support.

## -struct-fields

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

## -see-also

[**D3DKMTCheckMultiPlaneOverlaySupport**](nf-d3dkmthk-d3dkmtcheckmultiplaneoverlaysupport.md)
