---
UID: NS:d3d12umddi.D3D12DDI_WRITEBUFFERIMMEDIATE_PARAMETER_0032
title: D3D12DDI_WRITEBUFFERIMMEDIATE_PARAMETER_0032
author: windows-driver-content
description: Write buffer immediate parameter.
old-location: display\d3d12ddi-writebufferimmediate-parameter-0032.htm
old-project: display
ms.assetid: 84b0f28d-2157-492e-bafa-ea97956d66f2
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_WRITEBUFFERIMMEDIATE_PARAMETER_0032 structure [Display Devices], display.d3d12ddi-writebufferimmediate-parameter-0032, D3D12DDI_WRITEBUFFERIMMEDIATE_PARAMETER_0032, d3d12umddi/D3D12DDI_WRITEBUFFERIMMEDIATE_PARAMETER_0032
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	D3D12DDI_WRITEBUFFERIMMEDIATE_PARAMETER_0032
product: Windows
targetos: Windows
req.typenames: D3D12DDI_WRITEBUFFERIMMEDIATE_PARAMETER_0032
---

# D3D12DDI_WRITEBUFFERIMMEDIATE_PARAMETER_0032 structure


## -description


Write buffer immediate parameter.


## -syntax


````
typedef struct _D3D12DDI_WRITEBUFFERIMMEDIATE_PARAMETER_0032 {
  D3D12DDI_GPU_VIRTUAL_ADDRESS  Dst;
  UINT32                        Value;
} D3D12DDI_WRITEBUFFERIMMEDIATE_PARAMETER_0032, D3D12DDI_WRITEBUFFERIMMEDIATE_PARAMETER_0032;
````


## -struct-fields




### -field Dst

Destination.


### -field Value

Value.

