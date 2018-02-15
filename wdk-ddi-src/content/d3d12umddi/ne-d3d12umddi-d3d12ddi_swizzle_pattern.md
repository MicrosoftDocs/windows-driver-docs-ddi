---
UID: NE:d3d12umddi.D3D12DDI_SWIZZLE_PATTERN
title: D3D12DDI_SWIZZLE_PATTERN
author: windows-driver-content
description: Specifies a swizzle pattern.
old-location: display\d3d12ddi_swizzle_pattern.htm
old-project: display
ms.assetid: 2C51BB44-3204-4EE8-9C86-605698BD58C0
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3d12umddi/D3D12DDI_SP_64KB_STANDARD_SWIZZLE, D3D12DDI_SWIZZLE_PATTERN, d3d12umddi/D3D12DDI_SWIZZLE_PATTERN, D3D12DDI_SP_DEVICE_DEPENDENT_0, D3D12DDI_SP_ROW_MAJOR, d3d12umddi/D3D12DDI_SP_DEVICE_DEPENDENT_0, D3D12DDI_SWIZZLE_PATTERN enumeration [Display Devices], display.d3d12ddi_swizzle_pattern, D3D12DDI_SP_64KB_STANDARD_SWIZZLE, d3d12umddi/D3D12DDI_SP_ROW_MAJOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	D3D12DDI_SWIZZLE_PATTERN
product: Windows
targetos: Windows
req.typenames: D3D12DDI_SWIZZLE_PATTERN
---

# D3D12DDI_SWIZZLE_PATTERN enumeration


## -description


Specifies a swizzle pattern.


## -syntax


````
typedef enum D3D12DDI_SWIZZLE_PATTERN { 
  D3D12DDI_SP_ROW_MAJOR              = 0,
  D3D12DDI_SP_64KB_STANDARD_SWIZZLE  = 3,
  D3D12DDI_SP_DEVICE_DEPENDENT_0     = 0x100
} D3D12DDI_SWIZZLE_PATTERN;
````


## -enum-fields




### -field D3D12DDI_SP_ROW_MAJOR

A row major swizzle pattern.


### -field D3D12DDI_SP_64KB_STANDARD_SWIZZLE

A 64 KB standard swizzle pattern.


### -field D3D12DDI_SP_DEVICE_DEPENDENT_0

A device dependant swizzle pattern. 

