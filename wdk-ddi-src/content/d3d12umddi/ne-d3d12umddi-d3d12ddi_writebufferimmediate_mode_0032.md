---
UID: NE:d3d12umddi.D3D12DDI_WRITEBUFFERIMMEDIATE_MODE_0032
title: D3D12DDI_WRITEBUFFERIMMEDIATE_MODE_0032
author: windows-driver-content
description: The write buffer immediate mode.
old-location: display\d3d12ddi-writebufferimmediate-mode-0032.htm
old-project: display
ms.assetid: 4d968e4c-fb5b-47d6-b4ca-5f9d1d9c4739
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_WRITEBUFFERIMMEDIATE_MODE_0032, D3D12DDI_WRITEBUFFERIMMEDIATE_MODE_MARKER_OUT, d3d12umddi/D3D12DDI_WRITEBUFFERIMMEDIATE_MODE_DEFAULT, D3D12DDI_WRITEBUFFERIMMEDIATE_MODE_0032 enumeration [Display Devices], D3D12DDI_WRITEBUFFERIMMEDIATE_MODE_DEFAULT, display.d3d12ddi-writebufferimmediate-mode-0032, d3d12umddi/D3D12DDI_WRITEBUFFERIMMEDIATE_MODE_MARKER_IN, d3d12umddi/D3D12DDI_WRITEBUFFERIMMEDIATE_MODE_MARKER_OUT, D3D12DDI_WRITEBUFFERIMMEDIATE_MODE_MARKER_IN, d3d12umddi/D3D12DDI_WRITEBUFFERIMMEDIATE_MODE_0032
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d12umddi.h
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
-	d3d12umddi.h
apiname:
-	D3D12DDI_WRITEBUFFERIMMEDIATE_MODE_0032
product: Windows
targetos: Windows
req.typenames: D3D12DDI_WRITEBUFFERIMMEDIATE_MODE_0032
---

# D3D12DDI_WRITEBUFFERIMMEDIATE_MODE_0032 enumeration


## -description


The write buffer immediate mode.


## -syntax


````
typedef enum _D3D12DDI_WRITEBUFFERIMMEDIATE_MODE_0032 { 
  D3D12DDI_WRITEBUFFERIMMEDIATE_MODE_DEFAULT,
  D3D12DDI_WRITEBUFFERIMMEDIATE_MODE_MARKER_IN,
  D3D12DDI_WRITEBUFFERIMMEDIATE_MODE_MARKER_OUT
} D3D12DDI_WRITEBUFFERIMMEDIATE_MODE_0032;
````


## -enum-fields




#### - D3D12DDI_WRITEBUFFERIMMEDIATE_MODE_DEFAULT

The write buffer immediate default value is 0x0.


#### - D3D12DDI_WRITEBUFFERIMMEDIATE_MODE_MARKER_IN

The write buffer immediate mode is marker in, and the value is 0x1.


#### - D3D12DDI_WRITEBUFFERIMMEDIATE_MODE_MARKER_OUT

The write buffer immediate  mode is marker out, and the value is 0x2.

