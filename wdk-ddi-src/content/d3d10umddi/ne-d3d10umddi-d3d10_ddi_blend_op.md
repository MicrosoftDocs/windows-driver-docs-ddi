---
UID: NE:d3d10umddi.D3D10_DDI_BLEND_OP
title: D3D10_DDI_BLEND_OP
author: windows-driver-content
description: The D3D10_DDI_BLEND_OP enumeration type contains values that identify blending operations in a call to the driver's CreateBlendState function.
old-location: display\d3d10_ddi_blend_op.htm
old-project: display
ms.assetid: 3743db2a-d613-4efb-ae73-80eb1bfd9410
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D10_DDI_BLEND_OP, D3D10_DDI_BLEND_OP
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
req.alt-api: D3D10_DDI_BLEND_OP
req.alt-loc: d3d10umddi.h
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
req.typenames: D3D10_DDI_BLEND_OP
---

# D3D10_DDI_BLEND_OP enumeration



## -description
The D3D10_DDI_BLEND_OP enumeration type contains values that identify blending operations in a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createblendstate.md">CreateBlendState</a> function.



## -syntax

````
typedef enum D3D10_DDI_BLEND_OP { 
  D3D10_DDI_BLEND_OP_ADD           = 1,
  D3D10_DDI_BLEND_OP_SUBTRACT      = 2,
  D3D10_DDI_BLEND_OP_REV_SUBTRACT  = 3,
  D3D10_DDI_BLEND_OP_MIN           = 4,
  D3D10_DDI_BLEND_OP_MAX           = 5
} D3D10_DDI_BLEND_OP;
````


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


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createblendstate.md">CreateBlendState</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_DDI_BLEND_OP enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

