---
UID: NS:d3d10umddi.D3D11_1DDIARG_SIGNATURE_ENTRY
title: D3D11_1DDIARG_SIGNATURE_ENTRY (d3d10umddi.h)
description: Describes an entry for a signature.
old-location: display\d3d11_1ddiarg_signature_entry.htm
ms.assetid: 571ed880-a4c6-4eb1-a254-c1faf2a589d2
ms.date: 05/10/2018
ms.keywords: D3D11_1DDIARG_SIGNATURE_ENTRY, D3D11_1DDIARG_SIGNATURE_ENTRY structure [Display Devices], d3d10umddi/D3D11_1DDIARG_SIGNATURE_ENTRY, display.d3d11_1ddiarg_signature_entry
f1_keywords:
 - "d3d10umddi/D3D11_1DDIARG_SIGNATURE_ENTRY"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- D3d10umddi.h
api_name:
- D3D11_1DDIARG_SIGNATURE_ENTRY
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDIARG_SIGNATURE_ENTRY
---

# D3D11_1DDIARG_SIGNATURE_ENTRY structure


## -description


Describes an entry for a signature.


## -struct-fields




### -field SystemValue

[in] The <b>D3D10_SB_NAME</b>-typed value that indicates the system name of the signature entry. The <b>D3D10_SB_NAME</b> enumeration is defined in the D3d10tokenizedprogramformat.hpp header file. One of the following values can be set.

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


### -field RegisterComponentType

A  <b>D3D10_SB_REGISTER_COMPONENT_TYPE</b> type that indicates the register component type.

The <b>D3D10_SB_REGISTER_COMPONENT_TYPE</b> enumeration is defined in the D3d10tokenizedprogramformat.hpp header file.


### -field MinPrecision

A <b>D3D11_SB_OPERAND_MIN_PRECISION</b> type that indicates a minimum precision of source and destination operands.

The <b>D3D11_SB_OPERAND_MIN_PRECISION</b> enumeration is defined in the D3d10tokenizedprogramformat.hpp header file.

