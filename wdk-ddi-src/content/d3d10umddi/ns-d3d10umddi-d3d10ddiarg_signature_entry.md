---
UID: NS:d3d10umddi.D3D10DDIARG_SIGNATURE_ENTRY
title: D3D10DDIARG_SIGNATURE_ENTRY (d3d10umddi.h)
description: The D3D10DDIARG_SIGNATURE_ENTRY structure describes an entry for a signature.
old-location: display\d3d10ddiarg_signature_entry.htm
ms.assetid: 9a7a595e-59b1-4cc2-ab09-ba22aebae9ca
ms.date: 05/10/2018
ms.keywords: D3D10DDIARG_SIGNATURE_ENTRY, D3D10DDIARG_SIGNATURE_ENTRY structure [Display Devices], UMDisplayDriver_Dx10param_Structs_8f54c330-f382-4bae-939f-7b96fd9b1a46.xml, d3d10umddi/D3D10DDIARG_SIGNATURE_ENTRY, display.d3d10ddiarg_signature_entry
f1_keywords:
 - "d3d10umddi/D3D10DDIARG_SIGNATURE_ENTRY"
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
- D3D10DDIARG_SIGNATURE_ENTRY
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D10DDIARG_SIGNATURE_ENTRY
---

# D3D10DDIARG_SIGNATURE_ENTRY structure


## -description


The D3D10DDIARG_SIGNATURE_ENTRY structure describes an entry for a signature.


## -struct-fields




### -field SystemValue

[in] The D3D10_SB_NAME-typed value that indicates the system name of the signature entry. The D3D10_SB_NAME enumeration is defined in the D3d10tokenizedprogramformat.hpp header file. One of the following values can be set.

|Value|System name|
|--- |--- |
|D3D10_SB_NAME_UNDEFINED (0)|The entry does not have a system name.|
|D3D10_SB_NAME_POSITION (1)|Position.|
|D3D10_SB_NAME_CLIP_DISTANCE (2)|Clip distance.|
|D3D10_SB_NAME_CULL_DISTANCE (3)|Cull distance.|
|D3D10_SB_NAME_RENDER_TARGET_ARRAY_INDEX (4)|Render target array index.|
|D3D10_SB_NAME_VIEWPORT_ARRAY_INDEX (5)|Viewport array index.|
|D3D10_SB_NAME_VERTEX_ID (6)|Vertex ID.|
|D3D10_SB_NAME_PRIMITIVE_ID (7)|Primitive ID.|
|D3D10_SB_NAME_INSTANCE_ID (8)|Instance ID.|
|D3D10_SB_NAME_IS_FRONT_FACE (9)|Is front face.|
 


### -field Register

[in] The number of the register for the signature entry.


### -field Mask

[in] The xyzw mask for the signature entry. The four least significant bits (LSBs) of the mask represent xyzw respectively.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_stage_io_signatures">D3D10DDIARG_STAGE_IO_SIGNATURES</a>
 

 

