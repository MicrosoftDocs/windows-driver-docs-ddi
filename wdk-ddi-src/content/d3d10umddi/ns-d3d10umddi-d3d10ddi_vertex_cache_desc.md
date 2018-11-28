---
UID: NS:d3d10umddi.D3D10DDI_VERTEX_CACHE_DESC
title: D3D10DDI_VERTEX_CACHE_DESC
author: windows-driver-content
description: The D3D10DDI_VERTEX_CACHE_DESC structure describes mesh-optimization data.
old-location: display\d3d10ddi_vertex_cache_desc.htm
ms.assetid: c6cff037-436c-4c7e-85b8-02c9d7827f95
ms.date: 05/10/2018
ms.keywords: D3D10DDI_VERTEX_CACHE_DESC, D3D10DDI_VERTEX_CACHE_DESC structure [Display Devices], UMDisplayDriver_Dx10param_Structs_585c3ccc-83c7-4d3b-903d-7eac81a1c21c.xml, d3d10umddi/D3D10DDI_VERTEX_CACHE_DESC, display.d3d10ddi_vertex_cache_desc
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3d10umddi.h
api_name:
-	D3D10DDI_VERTEX_CACHE_DESC
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D10DDI_VERTEX_CACHE_DESC
---

# D3D10DDI_VERTEX_CACHE_DESC structure


## -description


The D3D10DDI_VERTEX_CACHE_DESC structure describes mesh-optimization data.


## -struct-fields




### -field Pattern

[out] The bit pattern. The driver must specify the bit pattern as a CACH four-character code (FOURCC) value. The driver can use the following MAKEFOURCC macro to specify the FOURCC value as CACH:


```cpp
MAKEFOURCC('C', 'A', 'C', 'H'); 
```

### -field OptMethod

[out] The method of mesh optimization. The driver can use one of the following values to specify the mesh optimization that it uses.

|Value|Meaning|
|--- |--- |
|0|Longest strips optimization|
|1|Vertex-cache-based optimization|
 


### -field CacheSize

[out] The effective size, in entries, that the driver optimizes the vertex cache for. The actual cache size is not required to be the size that is specified in <b>CacheSize</b> because the actual cache size is larger in most situations. The driver specifies an optimized size in <b>CacheSize</b> only if it also specifies 1 in the <b>OptMethod</b> member.


### -field MagicNumber

[out] The number that should be used as part of a trial-and-error procedure when you are determining when to restart the strips list. This number can be from 1 through the value that is specified in the <b>CacheSize</b> member. Typically, the best values are near <b>CacheSize</b>/2. The driver specifies a number in <b>MagicNumber</b> only if it also specifies 0 in the <b>OptMethod</b> member. 

