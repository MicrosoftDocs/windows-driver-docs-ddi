---
UID: NS:d3dkmthk._D3DKMT_OUTPUTDUPL_GET_POINTER_SHAPE_DATA
title: D3DKMT_OUTPUTDUPL_GET_POINTER_SHAPE_DATA (d3dkmthk.h)
description: Learn more about the D3DKMT_OUTPUTDUPL_GET_POINTER_SHAPE_DATA structure.
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
req.typenames: D3DKMT_OUTPUTDUPL_GET_POINTER_SHAPE_DATA
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - _D3DKMT_OUTPUTDUPL_GET_POINTER_SHAPE_DATA
 - d3dkmthk/_D3DKMT_OUTPUTDUPL_GET_POINTER_SHAPE_DATA
 - D3DKMT_OUTPUTDUPL_GET_POINTER_SHAPE_DATA
 - d3dkmthk/D3DKMT_OUTPUTDUPL_GET_POINTER_SHAPE_DATA
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_OUTPUTDUPL_GET_POINTER_SHAPE_DATA
 - D3DKMT_OUTPUTDUPL_GET_POINTER_SHAPE_DATA
dev_langs:
 - c++
---

# D3DKMT_OUTPUTDUPL_GET_POINTER_SHAPE_DATA structure

## -description

The **D3DKMT_OUTPUTDUPL_GET_POINTER_SHAPE_DATA** structure contains pointer shape data.

## -struct-fields

### -field hAdapter

A handle to the graphics adapter.

### -field VidPnSourceId

The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the monitor is connected to.

### -field BufferSizeSupplied

The supplied buffer size.

### -field pShapeBuffer

A pointer to the shape buffer.

### -field BufferSizeRequired

The required buffer size.

### -field ShapeInfo

The shape info.

## -remarks

## -see-also
