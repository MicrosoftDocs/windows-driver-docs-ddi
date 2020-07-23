---
UID: NE:d3d10umddi.D3D10_DDI_BLEND_OP
title: D3D10_DDI_BLEND_OP (d3d10umddi.h)
description: The D3D10_DDI_BLEND_OP enumeration type contains values that identify blending operations in a call to the driver's CreateBlendState function.
old-location: display\d3d10_ddi_blend_op.htm
ms.assetid: 3743db2a-d613-4efb-ae73-80eb1bfd9410
ms.date: 05/10/2018
keywords: ["D3D10_DDI_BLEND_OP enumeration"]
ms.keywords: D3D10_DDI_BLEND_OP, D3D10_DDI_BLEND_OP enumeration [Display Devices], D3D10_DDI_BLEND_OP_ADD, D3D10_DDI_BLEND_OP_MAX, D3D10_DDI_BLEND_OP_MIN, D3D10_DDI_BLEND_OP_REV_SUBTRACT, D3D10_DDI_BLEND_OP_SUBTRACT, UMDisplayDriver_Dx10param_Structs_900c6f2c-fc2a-4982-a91e-b1ea29c5f0e4.xml, d3d10umddi/D3D10_DDI_BLEND_OP, d3d10umddi/D3D10_DDI_BLEND_OP_ADD, d3d10umddi/D3D10_DDI_BLEND_OP_MAX, d3d10umddi/D3D10_DDI_BLEND_OP_MIN, d3d10umddi/D3D10_DDI_BLEND_OP_REV_SUBTRACT, d3d10umddi/D3D10_DDI_BLEND_OP_SUBTRACT, display.d3d10_ddi_blend_op
f1_keywords:
 - "d3d10umddi/D3D10_DDI_BLEND_OP"
 - "D3D10_DDI_BLEND_OP"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d10umddi.h
api_name:
- D3D10_DDI_BLEND_OP
targetos: Windows
tech.root: display
req.typenames: D3D10_DDI_BLEND_OP
---

# D3D10_DDI_BLEND_OP enumeration


## -description


The D3D10_DDI_BLEND_OP enumeration type contains values that identify blending operations in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createblendstate">CreateBlendState</a> function.


## -enum-fields




### -field D3D10_DDI_BLEND_OP_ADD

The result is the destination added to the source (Result = Source + Destination). 


### -field D3D10_DDI_BLEND_OP_SUBTRACT

The result is the destination subtracted from to the source (Result = Source - Destination). 


### -field D3D10_DDI_BLEND_OP_REV_SUBTRACT

The result is the source subtracted from the destination (Result = Destination - Source). 


### -field D3D10_DDI_BLEND_OP_MIN

The result is the minimum of the source and destination (Result = MIN(Source, Destination)) 


### -field D3D10_DDI_BLEND_OP_MAX

The result is the maximum of the source and destination (Result = MAX(Source, Destination)) 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createblendstate">CreateBlendState</a>
 

 

