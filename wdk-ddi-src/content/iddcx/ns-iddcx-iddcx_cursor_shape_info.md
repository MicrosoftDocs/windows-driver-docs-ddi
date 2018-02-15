---
UID: NS:iddcx.IDDCX_CURSOR_SHAPE_INFO
title: IDDCX_CURSOR_SHAPE_INFO
author: windows-driver-content
description: Gives information about the shape of the cursor.
old-location: display\iddcx_cursor_shape_info.htm
old-project: display
ms.assetid: 58ed8f04-616f-4eea-b6e1-07f322c37dbb
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.iddcx_cursor_shape_info, iddcx/IDDCX_CURSOR_SHAPE_INFO, IDDCX_CURSOR_SHAPE_INFO structure [Display Devices], IDDCX_CURSOR_SHAPE_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	iddcx.h
apiname:
-	IDDCX_CURSOR_SHAPE_INFO
product: Windows
targetos: Windows
req.typenames: 
---

# IDDCX_CURSOR_SHAPE_INFO structure


## -description


Gives information about the shape of the cursor.


## -syntax


````
typedef struct IDDCX_CURSOR_SHAPE_INFO {
  UINT                    Size;
  UINT                    ShapeId;
  IDDCX_CURSOR_SHAPE_TYPE CursorType;
  UINT                    Width;
  UINT                    Height;
  UINT                    Pitch;
  UINT                    XHot;
  UINT                    YHot;
} IDDCX_CURSOR_SHAPE_INFO, *IDDCX_CURSOR_SHAPE_INFO;
````


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
                 

