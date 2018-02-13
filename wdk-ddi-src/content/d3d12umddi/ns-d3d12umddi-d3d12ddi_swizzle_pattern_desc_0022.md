---
UID: NS:d3d12umddi.D3D12DDI_SWIZZLE_PATTERN_DESC_0022
title: D3D12DDI_SWIZZLE_PATTERN_DESC_0022
author: windows-driver-content
description: Describes a swizzle pattern.
old-location: display\d3d12ddi_swizzle_pattern_desc_0022.htm
old-project: display
ms.assetid: A52C8293-C037-4062-9A63-AD69237F7B3D
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_SWIZZLE_PATTERN_DESC_0022 structure [Display Devices], D3D12DDI_SWIZZLE_PATTERN_DESC_0022, display.d3d12ddi_swizzle_pattern_desc_0022, d3d12umddi/D3D12DDI_SWIZZLE_PATTERN_DESC_0022
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
-	D3D12DDI_SWIZZLE_PATTERN_DESC_0022
product: Windows
targetos: Windows
req.typenames: D3D12DDI_SWIZZLE_PATTERN_DESC_0022
---

# D3D12DDI_SWIZZLE_PATTERN_DESC_0022 structure


## -description


Describes a swizzle pattern. 


## -syntax


````
typedef struct D3D12DDI_SWIZZLE_PATTERN_DESC_0022 {
  D3D12DDI_SWIZZLE_BIT_ENTRY InterleavePatternSourceBits[32];
  D3D12DDI_SWIZZLE_BIT_ENTRY InterleavePatternXORSourceBits[32];
  D3D12DDI_SWIZZLE_BIT_ENTRY InterleavePatternXOR2SourceBits[32];
  D3D12DDI_SWIZZLE_BIT_ENTRY InterleavePatternXOR3SourceBits[32];
  D3D12DDI_SWIZZLE_BIT_ENTRY InterleavePatternXOR4SourceBits[32];
  D3D12DDI_SWIZZLE_BIT_ENTRY PostambleXORSourceBits[32];
  D3D12DDI_SWIZZLE_BIT_ENTRY PostambleXOR2SourceBits[32];
  UINT                       PostambleXORImmediate;
  UINT                       Flags;
} D3D12DDI_SWIZZLE_PATTERN_DESC_0022;
````


## -struct-fields




### -field InterleavePatternSourceBits

The interleave pattern source bits.


### -field InterleavePatternXORSourceBits

The interleave pattern XOR source bits.


### -field InterleavePatternXOR2SourceBits

The interleave pattern second XOR source bits.


### -field InterleavePatternXOR3SourceBits

The interleave pattern third XOR source bits.


### -field InterleavePatternXOR4SourceBits

The interleave pattern fourth XOR source bits.


### -field PostambleXORSourceBits

Postamble XOR source bits.


### -field PostambleXOR2SourceBits

Postamble second XOR source bits.


### -field PostambleXORImmediate

A postamble XOR immediate value. 


### -field Flags

Flags. 

