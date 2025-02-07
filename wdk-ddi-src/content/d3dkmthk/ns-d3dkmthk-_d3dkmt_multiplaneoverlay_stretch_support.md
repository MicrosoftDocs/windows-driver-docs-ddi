---
UID: NS:d3dkmthk._D3DKMT_MULTIPLANEOVERLAY_STRETCH_SUPPORT
title: D3DKMT_MULTIPLANEOVERLAY_STRETCH_SUPPORT (d3dkmthk.h)
description: Learn more about the D3DKMT_MULTIPLANEOVERLAY_STRETCH_SUPPORT structure.
ms.date: 02/06/2025
req.header: d3dkmthk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1703 (WDDM 2.2)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3DKMT_MULTIPLANEOVERLAY_STRETCH_SUPPORT
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - _D3DKMT_MULTIPLANEOVERLAY_STRETCH_SUPPORT
 - d3dkmthk/_D3DKMT_MULTIPLANEOVERLAY_STRETCH_SUPPORT
 - D3DKMT_MULTIPLANEOVERLAY_STRETCH_SUPPORT
 - d3dkmthk/D3DKMT_MULTIPLANEOVERLAY_STRETCH_SUPPORT
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_MULTIPLANEOVERLAY_STRETCH_SUPPORT
 - D3DKMT_MULTIPLANEOVERLAY_STRETCH_SUPPORT
dev_langs:
 - c++
---

# D3DKMT_MULTIPLANEOVERLAY_STRETCH_SUPPORT structure

## -description

The **D3DKMT_MULTIPLANEOVERLAY_STRETCH_SUPPORT** structure describes the driver's multiplane overlay stretch support.

## -struct-fields

### -field VidPnSourceId

The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the monitor is connected to.

### -field Update

Boolean value that indicates whether to update.

### -field Supported

Boolean value that indicates whether multiplane overlay stretch is supported.

## -see-also

[D3DKMTQueryAdapterInfo](nf-d3dkmthk-d3dkmtqueryadapterinfo.md)
