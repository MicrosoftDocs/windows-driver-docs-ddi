---
UID: NS:d3dumddi.D3DDDICAPS_ARCHITECTURE_INFO
title: D3DDDICAPS_ARCHITECTURE_INFO (d3dumddi.h)
description: Describes information about display adapter architecture.
old-location: display\d3dddicaps_architecture_info.htm
tech.root: display
ms.assetid: ad35cd3f-87bd-4d57-ab13-4cb2b268ad35
ms.date: 05/10/2018
ms.keywords: D3DDDICAPS_ARCHITECTURE_INFO, D3DDDICAPS_ARCHITECTURE_INFO structure [Display Devices], d3dumddi/D3DDDICAPS_ARCHITECTURE_INFO, display.d3dddicaps_architecture_info
f1_keywords:
 - "d3dumddi/D3DDDICAPS_ARCHITECTURE_INFO"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3dumddi.h
api_name:
- D3DDDICAPS_ARCHITECTURE_INFO
product:
- Windows
targetos: Windows
req.typenames: D3DDDICAPS_ARCHITECTURE_INFO
---

# D3DDDICAPS_ARCHITECTURE_INFO structure


## -description


Describes information about display adapter architecture.


## -struct-fields




### -field TileBasedDeferredRenderer

Specifies whether a rendering device batches rendering commands and performs multipass rendering into tiles or bins over a render area. The value is <b>TRUE</b> if the rendering device batches rendering commands and <b>FALSE</b> otherwise.

