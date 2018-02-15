---
UID: NE:d3d10umddi.D3D10_DDI_STENCIL_OP
title: D3D10_DDI_STENCIL_OP
author: windows-driver-content
description: The D3D10_DDI_STENCIL_OP enumeration type contains values that identify operations on stencil buffers in a call to the driver's CreateDepthStencilState function.
old-location: display\d3d10_ddi_stencil_op.htm
old-project: display
ms.assetid: 624decb3-6279-45ba-8cdd-5a52de80dd71
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D10_DDI_STENCIL_OP_INCR_SAT, D3D10_DDI_STENCIL_OP, display.d3d10_ddi_stencil_op, D3D10_DDI_STENCIL_OP_ZERO, d3d10umddi/D3D10_DDI_STENCIL_OP_KEEP, D3D10_DDI_STENCIL_OP_DECR_SAT, d3d10umddi/D3D10_DDI_STENCIL_OP_DECR, D3D10_DDI_STENCIL_OP_INCR, D3D10_DDI_STENCIL_OP_DECR, UMDisplayDriver_Dx10param_Structs_0d70cbc2-b62c-4dce-b1f4-65b4c99ed5d7.xml, D3D10_DDI_STENCIL_OP enumeration [Display Devices], d3d10umddi/D3D10_DDI_STENCIL_OP_INCR, D3D10_DDI_STENCIL_OP_REPLACE, D3D10_DDI_STENCIL_OP_KEEP, d3d10umddi/D3D10_DDI_STENCIL_OP_ZERO, d3d10umddi/D3D10_DDI_STENCIL_OP_INVERT, d3d10umddi/D3D10_DDI_STENCIL_OP_DECR_SAT, d3d10umddi/D3D10_DDI_STENCIL_OP_INCR_SAT, d3d10umddi/D3D10_DDI_STENCIL_OP_REPLACE, D3D10_DDI_STENCIL_OP_INVERT, d3d10umddi/D3D10_DDI_STENCIL_OP
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3d10umddi.h
apiname:
-	D3D10_DDI_STENCIL_OP
product: Windows
targetos: Windows
req.typenames: D3D10_DDI_STENCIL_OP
---

# D3D10_DDI_STENCIL_OP enumeration


## -description


The D3D10_DDI_STENCIL_OP enumeration type contains values that identify operations on stencil buffers in a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdepthstencilstate.md">CreateDepthStencilState</a> function.


## -syntax


````
typedef enum D3D10_DDI_STENCIL_OP { 
  D3D10_DDI_STENCIL_OP_KEEP      = 1,
  D3D10_DDI_STENCIL_OP_ZERO      = 2,
  D3D10_DDI_STENCIL_OP_REPLACE   = 3,
  D3D10_DDI_STENCIL_OP_INCR_SAT  = 4,
  D3D10_DDI_STENCIL_OP_DECR_SAT  = 5,
  D3D10_DDI_STENCIL_OP_INVERT    = 6,
  D3D10_DDI_STENCIL_OP_INCR      = 7,
  D3D10_DDI_STENCIL_OP_DECR      = 8
} D3D10_DDI_STENCIL_OP;
````


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

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdepthstencilstate.md">CreateDepthStencilState</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_DDI_STENCIL_OP enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

