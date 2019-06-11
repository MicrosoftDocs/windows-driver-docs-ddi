---
UID: NE:d3d9types._D3DSHADER_PARAM_REGISTER_TYPE
title: _D3DSHADER_PARAM_REGISTER_TYPE (d3d9types.h)
description: Pixel and vertex shader operations specify register types in bits 28, 29, 30, 11, and 12 of destination and source parameter tokens.
old-location: display\shader_register_types.htm
tech.root: display
ms.assetid: e1763ae1-5583-43fe-a342-3b9b5a92ef3f
ms.date: 05/10/2018
ms.keywords: D3DSHADER_PARAM_REGISTER_TYPE, D3DSHADER_PARAM_REGISTER_TYPE enumeration [Display Devices], D3DSPR_ADDR, D3DSPR_ATTROUT, D3DSPR_COLOROUT, D3DSPR_CONST, D3DSPR_CONST2, D3DSPR_CONST3, D3DSPR_CONST4, D3DSPR_CONSTBOOL, D3DSPR_CONSTINT, D3DSPR_DEPTHOUT, D3DSPR_FORCE_DWORD, D3DSPR_INPUT, D3DSPR_LABEL, D3DSPR_LOOP, D3DSPR_MISCTYPE, D3DSPR_OUTPUT, D3DSPR_PREDICATE, D3DSPR_RASTOUT, D3DSPR_SAMPLER, D3DSPR_TEMP, D3DSPR_TEMPFLOAT16, D3DSPR_TEXCRDOUT, D3DSPR_TEXTURE, UserModeDisplayDriver_Shader_1968e381-80d3-44f2-a02d-7625ba93f95a.xml, _D3DSHADER_PARAM_REGISTER_TYPE, d3d9types/ D3DSPR_CONST, d3d9types/D3DSHADER_PARAM_REGISTER_TYPE, d3d9types/D3DSPR_ADDR, d3d9types/D3DSPR_ATTROUT, d3d9types/D3DSPR_COLOROUT, d3d9types/D3DSPR_CONST2, d3d9types/D3DSPR_CONST3, d3d9types/D3DSPR_CONST4, d3d9types/D3DSPR_CONSTBOOL, d3d9types/D3DSPR_CONSTINT, d3d9types/D3DSPR_DEPTHOUT, d3d9types/D3DSPR_FORCE_DWORD, d3d9types/D3DSPR_INPUT, d3d9types/D3DSPR_LABEL, d3d9types/D3DSPR_LOOP, d3d9types/D3DSPR_MISCTYPE, d3d9types/D3DSPR_OUTPUT, d3d9types/D3DSPR_PREDICATE, d3d9types/D3DSPR_RASTOUT, d3d9types/D3DSPR_SAMPLER, d3d9types/D3DSPR_TEMP, d3d9types/D3DSPR_TEMPFLOAT16, d3d9types/D3DSPR_TEXCRDOUT, d3d9types/D3DSPR_TEXTURE, display.shader_register_types
ms.topic: enum
req.header: d3d9types.h
req.include-header: 
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
- d3d9types.h
api_name:
- D3DSHADER_PARAM_REGISTER_TYPE
product:
- Windows
targetos: Windows
req.typenames: D3DSHADER_PARAM_REGISTER_TYPE
---

# _D3DSHADER_PARAM_REGISTER_TYPE enumeration


## -description


Pixel and vertex shader operations specify shader register types in bits 28, 29, 30, 11, and 12 of destination and source parameter tokens. The following register types can be specified:


## -enum-fields




### -field D3DSPR_TEMP

Temporary register file.


### -field D3DSPR_INPUT

Input register file.


### -field D3DSPR_CONST

For PS, constant register file  0 - 2047 (DEF instruction). For VS, reserved.


### -field D3DSPR_ADDR

Address register (VS).


### -field D3DSPR_TEXTURE

Texture register file (PS).


### -field D3DSPR_RASTOUT

For VS, rasterizer output register file.


### -field D3DSPR_ATTROUT

Attribute output register file.


### -field D3DSPR_TEXCRDOUT

Texture coordinate output register file.


### -field D3DSPR_OUTPUT

For &lt; VS 3_0, texture coordinate output register file. For &gt;/= VS 3_0, output register file. For PS, reserved.


### -field D3DSPR_CONSTINT

Constant integer vector register file.


### -field D3DSPR_COLOROUT

Color output register file.


### -field D3DSPR_DEPTHOUT

Depth output register file.


### -field D3DSPR_SAMPLER

Sampler state register file.


### -field D3DSPR_CONST2

Constant register file  2048 - 4095.


### -field D3DSPR_CONST3

Constant register file  4096 - 6143.


### -field D3DSPR_CONST4

Constant register file  6144 - 8191.


### -field D3DSPR_CONSTBOOL

Constant Boolean register file.


### -field D3DSPR_LOOP

Loop counter register file.


### -field D3DSPR_TEMPFLOAT16

16-bit float temp register file.


### -field D3DSPR_MISCTYPE

Miscellaneous (single) registers.


### -field D3DSPR_LABEL

Label.


### -field D3DSPR_PREDICATE

Predicate register.


### -field D3DSPR_FORCE_DWORD

Force 32-bit size enumeration.

