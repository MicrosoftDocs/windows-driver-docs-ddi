---
UID: NS:iddcx.IDDCX_CURSOR_SHAPE_INFO
title: IDDCX_CURSOR_SHAPE_INFO (iddcx.h)
description: Gives information about the shape of the cursor.
old-location: display\iddcx_cursor_shape_info.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["IDDCX_CURSOR_SHAPE_INFO structure"]
ms.keywords: IDDCX_CURSOR_SHAPE_INFO, IDDCX_CURSOR_SHAPE_INFO structure [Display Devices], display.iddcx_cursor_shape_info, iddcx/IDDCX_CURSOR_SHAPE_INFO
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
 - IDDCX_CURSOR_SHAPE_INFO
 - iddcx/IDDCX_CURSOR_SHAPE_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_CURSOR_SHAPE_INFO
---

# IDDCX_CURSOR_SHAPE_INFO structure


## -description

Gives information about the shape of the cursor.

## -struct-fields

### -field Size

                     Total size of the structure.

### -field ShapeId

                     Unique id for the current cursor image. This is incremented each time a cursor image is set, even if that image has been set before. The id is used to check if the current cursor image the driver has cached has changed and cannot be used in any way to allow caching for animated cursor sequences.

### -field CursorType

                     Indicates the type of cursor data written to the cursor shape buffer.

### -field Width

                     Width in pixels of the cursor shape written to the shape buffer.

### -field Height

                     Height in pixels of the cursor shape written to the shape buffer.

### -field Pitch

                     Pitch in bytes of the cursor shape written to the shape buffer.

### -field XHot

                     X position of the cursor hotspot relative to the top-left of the cursor.

### -field YHot

                     Y position of the cursor hotspot relative to the top-left of the cursor.

