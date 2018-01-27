---
UID: NS:d3dumddi.D3DDDICAPS_ARCHITECTURE_INFO
title: D3DDDICAPS_ARCHITECTURE_INFO
author: windows-driver-content
description: Describes information about display adapter architecture.
old-location: display\d3dddicaps_architecture_info.htm
old-project: display
ms.assetid: ad35cd3f-87bd-4d57-ab13-4cb2b268ad35
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDICAPS_ARCHITECTURE_INFO, d3dumddi/D3DDDICAPS_ARCHITECTURE_INFO, display.d3dddicaps_architecture_info, D3DDDICAPS_ARCHITECTURE_INFO structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	D3dumddi.h
apiname: 
-	D3DDDICAPS_ARCHITECTURE_INFO
product: Windows
targetos: Windows
req.typenames: D3DDDICAPS_ARCHITECTURE_INFO
---

# D3DDDICAPS_ARCHITECTURE_INFO structure


## -description


Describes information about display adapter architecture.


## -syntax


````
typedef struct D3DDDICAPS_ARCHITECTURE_INFO {
  BOOL TileBasedDeferredRenderer;
} D3DDDICAPS_ARCHITECTURE_INFO;
````


## -struct-fields




### -field TileBasedDeferredRenderer

Specifies whether a rendering device batches rendering commands and performs multipass rendering into tiles or bins over a render area. The value is <b>TRUE</b> if the rendering device batches rendering commands and <b>FALSE</b> otherwise.

