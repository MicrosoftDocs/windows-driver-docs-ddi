---
UID: NS:d3dkmdt._D3DKMDT_2DREGION
title: _D3DKMDT_2DREGION
author: windows-driver-content
description: The D3DKMDT_2DREGION structure is used to represent a point or an offset in a two-dimensional space.
old-location: display\d3dkmdt_2dregion.htm
old-project: display
ms.assetid: 24f703c5-d025-4233-a32d-7cb8bcb5c6b7
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMDT_2DREGION, D3DKMDT_2DREGION, D3DKMDT_2DOFFSET
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMDT_2DREGION
req.alt-loc: d3dkmdt.h
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
req.typenames: D3DKMDT_2DREGION
---

# _D3DKMDT_2DREGION structure



## -description
The D3DKMDT_2DREGION structure is used to represent a point or an offset in a two-dimensional space.



## -syntax

````
typedef struct _D3DKMDT_2DREGION {
  UINT cx;
  UINT cy;
} D3DKMDT_2DREGION;
````


## -struct-fields

### -field cx

The horizontal component of the point or offset.


### -field cy

The vertical component of the point or offset.


## -remarks
