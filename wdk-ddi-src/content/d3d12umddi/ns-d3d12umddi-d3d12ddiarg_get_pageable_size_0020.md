---
UID: NS:d3d12umddi.D3D12DDIARG_GET_PAGEABLE_SIZE_0020
title: D3D12DDIARG_GET_PAGEABLE_SIZE_0020
author: windows-driver-content
description: Specifies information used to get the driver reported size for an array of allocations.
old-location: display\d3d12ddiarg_get_pageable_size.htm
old-project: display
ms.assetid: 82A5ACBD-EE18-46DF-822B-87ABF331BF44
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDIARG_GET_PAGEABLE_SIZE_0020 structure [Display Devices], D3D12DDIARG_GET_PAGEABLE_SIZE_0020, d3d12umddi/D3D12DDIARG_GET_PAGEABLE_SIZE_0020, display.d3d12ddiarg_get_pageable_size
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
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
-	D3d12umddi.h
apiname:
-	D3D12DDIARG_GET_PAGEABLE_SIZE_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDIARG_GET_PAGEABLE_SIZE_0020
---

# D3D12DDIARG_GET_PAGEABLE_SIZE_0020 structure


## -description


Specifies information used to get the driver reported size for an array of allocations.


## -syntax


````
typedef struct D3D12DDIARG_GET_PAGEABLE_SIZE_0020 {
  UINT                                                    NumObjects;
  _Field_size_(NumObjects) CONST D3D12DDI_HANDLE_AND_TYPE *pObjects;
} D3D12DDIARG_GET_PAGEABLE_SIZE_0020;
````


## -struct-fields




### -field NumObjects

The number of objects for which to get the pageable size.


### -field pObjects

The array of objects for which to get the pageable size.

