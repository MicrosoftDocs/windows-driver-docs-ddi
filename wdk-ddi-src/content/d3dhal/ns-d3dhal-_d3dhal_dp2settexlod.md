---
UID: NS:d3dhal._D3DHAL_DP2SETTEXLOD
title: "_D3DHAL_DP2SETTEXLOD"
author: windows-driver-content
description: The D3DHAL_DP2SETTEXLOD structure is used to set the level of detail (LOD) for MIP maps when the D3DDP2OP_SETTEXLOD command is sent to D3dDrawPrimitives2.
old-location: display\d3dhal_dp2settexlod.htm
old-project: display
ms.assetid: 89fc8319-64ec-4e9d-8863-e5140e9f7a44
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*LPD3DHAL_DP2SETTEXLOD, D3DHAL_DP2SETTEXLOD, D3DHAL_DP2SETTEXLOD structure [Display Devices], _D3DHAL_DP2SETTEXLOD, d3dhal/D3DHAL_DP2SETTEXLOD, d3dstrct_8b7c348f-b058-4cd8-ac49-788765e4fa15.xml, display.d3dhal_dp2settexlod"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dhal.h
api_name:
-	D3DHAL_DP2SETTEXLOD
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2SETTEXLOD
---

# _D3DHAL_DP2SETTEXLOD structure


## -description


The D3DHAL_DP2SETTEXLOD structure is used to set the level of detail (LOD) for MIP maps when the D3DDP2OP_SETTEXLOD command is sent to <a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a>.


## -struct-fields




### -field dwDDSurface

Specifies a handle to a surface chain.


### -field dwLOD

Controls the maximum MIP level loaded into video memory. Therefore, if the most detailed MIP map in the chain has dimensions 256x256, setting the maximum level to 2 means that the largest MIP map ever present in video memory has dimensions 64x64. 


## -remarks




     Used only for driver-managed textures. This structure contains a surface handle to the MIP map and the maximum level of detail to set.




## -see-also




D3DDP2OP_SETTEXLOD



<a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a>
 

 

