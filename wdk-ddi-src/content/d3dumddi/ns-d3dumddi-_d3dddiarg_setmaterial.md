---
UID: NS:d3dumddi._D3DDDIARG_SETMATERIAL
title: _D3DDDIARG_SETMATERIAL (d3dumddi.h)
description: The D3DDDIARG_SETMATERIAL structure describes the material properties that are used for rendering.
old-location: display\d3dddiarg_setmaterial.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDDIARG_SETMATERIAL structure"]
ms.keywords: D3DDDIARG_SETMATERIAL, D3DDDIARG_SETMATERIAL structure [Display Devices], UMDisplayDriver_param_Structs_5a3ecda9-5303-46f4-b7a2-42243e3a66d1.xml, _D3DDDIARG_SETMATERIAL, d3dumddi/D3DDDIARG_SETMATERIAL, display.d3dddiarg_setmaterial
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
req.typenames: D3DDDIARG_SETMATERIAL
f1_keywords:
 - _D3DDDIARG_SETMATERIAL
 - d3dumddi/_D3DDDIARG_SETMATERIAL
 - D3DDDIARG_SETMATERIAL
 - d3dumddi/D3DDDIARG_SETMATERIAL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - D3DDDIARG_SETMATERIAL
---

# _D3DDDIARG_SETMATERIAL structure


## -description

The D3DDDIARG_SETMATERIAL structure describes the material properties that are used for rendering.

## -struct-fields

### -field Diffuse

[in] A D3DCOLORVALUE structure that indicates the diffuse color of the material. For more information about D3DCOLORVALUE, see the Microsoft Windows SDK documentation.

### -field Ambient

[in] A D3DCOLORVALUE structure that indicates the ambient color of the material.

### -field Specular

[in] A D3DCOLORVALUE structure that indicates the specular color of the material.

### -field Emissive

[in] A D3DCOLORVALUE structure that indicates the emissive color of the material.

### -field Power

[in] A FLOAT value that indicates the sharpness of specular highlights. To turn off specular highlights for a material, set <b>Power</b> to 0 (setting <b>Specular</b> to 0 is not enough).

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_setmaterial">SetMaterial</a>
