---
UID: NE:d3dukmdt.D3DDDI_SCANLINEORDERING
title: D3DDDI_SCANLINEORDERING
author: windows-driver-content
description: The D3DDDI_SCANLINEORDERING enumeration type contains values that identify how the scan lines are drawn on a surface.
old-location: display\d3dddi_scanlineordering.htm
old-project: display
ms.assetid: 6b7b0bbf-79f2-4b0c-a7e6-75dc92bf8a63
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDI_SCANLINEORDERING, D3DDDI_SCANLINEORDERING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDI_SCANLINEORDERING is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDI_SCANLINEORDERING
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
req.typenames: D3DDDI_SCANLINEORDERING
---

# D3DDDI_SCANLINEORDERING enumeration



## -description
The D3DDDI_SCANLINEORDERING enumeration type contains values that identify how the scan lines are drawn on a surface. 



## -syntax

````
typedef enum D3DDDI_SCANLINEORDERING { 
  D3DDDI_SCANLINEORDERING_UNKNOWN      = 0,
  D3DDDI_SCANLINEORDERING_PROGRESSIVE  = 1,
  D3DDDI_SCANLINEORDERING_INTERLACED   = 2
} D3DDDI_SCANLINEORDERING;
````


## -enum-fields

### -field D3DDDI_SCANLINEORDERING_UNKNOWN

The value indicates that scan-line ordering is unknown. 


### -field D3DDDI_SCANLINEORDERING_PROGRESSIVE

The value indicates that scan-line ordering is progressive. 


### -field D3DDDI_SCANLINEORDERING_INTERLACED

The value indicates that scan-line ordering is interlaced. 


## -remarks
