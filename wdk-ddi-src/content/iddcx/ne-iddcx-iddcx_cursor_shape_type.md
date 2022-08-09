---
UID: NE:iddcx.IDDCX_CURSOR_SHAPE_TYPE
title: IDDCX_CURSOR_SHAPE_TYPE (iddcx.h)
description: Describes the type of cursor.
old-location: display\iddcx_cursor_shape_type.htm
tech.root: display
ms.date: 08/08/2022
keywords: ["IDDCX_CURSOR_SHAPE_TYPE enumeration"]
ms.keywords: IDDCX_CURSOR_SHAPE_TYPE, IDDCX_CURSOR_SHAPE_TYPE enumeration [Display Devices], IDDCX_CURSOR_SHAPE_TYPE_ALPHA, IDDCX_CURSOR_SHAPE_TYPE_MASKED_COLOR, IDDCX_CURSOR_SHAPE_TYPE_UNINITIALIZED, display.iddcx_cursor_shape_type, iddcx/IDDCX_CURSOR_SHAPE_TYPE, iddcx/IDDCX_CURSOR_SHAPE_TYPE_ALPHA, iddcx/IDDCX_CURSOR_SHAPE_TYPE_MASKED_COLOR, iddcx/IDDCX_CURSOR_SHAPE_TYPE_UNINITIALIZED
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IDDCX_CURSOR_SHAPE_TYPE
 - iddcx/IDDCX_CURSOR_SHAPE_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_CURSOR_SHAPE_TYPE
---

# IDDCX_CURSOR_SHAPE_TYPE enumeration

## -description

A **IDDCX_CURSOR_SHAPE_TYPE** value describes the type of cursor data written to the cursor shape buffer.

## -enum-fields

### -field IDDCX_CURSOR_SHAPE_TYPE_UNINITIALIZED:0

The cursor shape is uninitialized.

### -field IDDCX_CURSOR_SHAPE_TYPE_MASKED_COLOR:1

This is a masked-color cursor shape.

### -field IDDCX_CURSOR_SHAPE_TYPE_ALPHA:2

This is a 32bpp alpha cursor.

## -see-also

[**IDDCX_CURSOR_SHAPE_INFO**](ns-iddcx-iddcx_cursor_shape_info.md)
