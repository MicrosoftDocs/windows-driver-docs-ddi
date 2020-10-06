---
UID: NE:d3d10umddi.D3D10_DDI_STENCIL_OP
title: D3D10_DDI_STENCIL_OP (d3d10umddi.h)
description: The D3D10_DDI_STENCIL_OP enumeration type contains values that identify operations on stencil buffers in a call to the driver's CreateDepthStencilState function.
old-location: display\d3d10_ddi_stencil_op.htm
ms.assetid: 624decb3-6279-45ba-8cdd-5a52de80dd71
ms.date: 05/10/2018
keywords: ["D3D10_DDI_STENCIL_OP enumeration"]
ms.keywords: D3D10_DDI_STENCIL_OP, D3D10_DDI_STENCIL_OP enumeration [Display Devices], D3D10_DDI_STENCIL_OP_DECR, D3D10_DDI_STENCIL_OP_DECR_SAT, D3D10_DDI_STENCIL_OP_INCR, D3D10_DDI_STENCIL_OP_INCR_SAT, D3D10_DDI_STENCIL_OP_INVERT, D3D10_DDI_STENCIL_OP_KEEP, D3D10_DDI_STENCIL_OP_REPLACE, D3D10_DDI_STENCIL_OP_ZERO, UMDisplayDriver_Dx10param_Structs_0d70cbc2-b62c-4dce-b1f4-65b4c99ed5d7.xml, d3d10umddi/D3D10_DDI_STENCIL_OP, d3d10umddi/D3D10_DDI_STENCIL_OP_DECR, d3d10umddi/D3D10_DDI_STENCIL_OP_DECR_SAT, d3d10umddi/D3D10_DDI_STENCIL_OP_INCR, d3d10umddi/D3D10_DDI_STENCIL_OP_INCR_SAT, d3d10umddi/D3D10_DDI_STENCIL_OP_INVERT, d3d10umddi/D3D10_DDI_STENCIL_OP_KEEP, d3d10umddi/D3D10_DDI_STENCIL_OP_REPLACE, d3d10umddi/D3D10_DDI_STENCIL_OP_ZERO, display.d3d10_ddi_stencil_op
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
targetos: Windows
tech.root: display
req.typenames: D3D10_DDI_STENCIL_OP
f1_keywords:
 - D3D10_DDI_STENCIL_OP
 - d3d10umddi/D3D10_DDI_STENCIL_OP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3D10_DDI_STENCIL_OP
---

# D3D10_DDI_STENCIL_OP enumeration


## -description

The D3D10_DDI_STENCIL_OP enumeration type contains values that identify operations on stencil buffers in a call to the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdepthstencilstate">CreateDepthStencilState</a> function.

## -enum-fields

### -field D3D10_DDI_STENCIL_OP_KEEP

Do not update the entry in the stencil buffer. D3D10_DDI_STENCIL_OP_KEEP is the default value.

### -field D3D10_DDI_STENCIL_OP_ZERO

Set the stencil-buffer entry to 0.

### -field D3D10_DDI_STENCIL_OP_REPLACE

Replace the stencil-buffer entry with a reference value.

### -field D3D10_DDI_STENCIL_OP_INCR_SAT

Increment the stencil-buffer entry, clamping to the maximum value.

### -field D3D10_DDI_STENCIL_OP_DECR_SAT

Decrement the stencil-buffer entry, clamping to zero.

### -field D3D10_DDI_STENCIL_OP_INVERT

Invert the bits in the stencil-buffer entry.

### -field D3D10_DDI_STENCIL_OP_INCR

Increment the stencil-buffer entry, wrapping to zero if the new value exceeds the maximum value.

### -field D3D10_DDI_STENCIL_OP_DECR

Decrement the stencil-buffer entry, wrapping to the maximum value if the new value is less than zero.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdepthstencilstate">CreateDepthStencilState</a>