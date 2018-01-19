---
UID: NS:d3dukmdt._DXGKVGPU_ESCAPE_READ_VGPU_TYPE
title: _DXGKVGPU_ESCAPE_READ_VGPU_TYPE
author: windows-driver-content
description: A structure used to read the VGPU type of an escape.
old-location: display\dxgkvgpu_escape_read_vgpu_type.htm
old-project: display
ms.assetid: 2D3D8927-74E3-438F-94CF-63456C7C7BBC
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGKVGPU_ESCAPE_READ_VGPU_TYPE, DXGKVGPU_ESCAPE_READ_VGPU_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKVGPU_ESCAPE_READ_VGPU_TYPE
req.alt-loc: d3dukmdt.h
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
req.typenames: DXGKVGPU_ESCAPE_READ_VGPU_TYPE
---

# _DXGKVGPU_ESCAPE_READ_VGPU_TYPE structure



## -description
A structure used to read the VGPU type of an escape.



## -syntax

````
typedef struct _DXGKVGPU_ESCAPE_READ_VGPU_TYPE {
  DXGKVGPU_ESCAPE_HEAD Header;
} DXGKVGPU_ESCAPE_READ_VGPU_TYPE;
````


## -struct-fields

### -field Header

The header that is being processed.


## -remarks
