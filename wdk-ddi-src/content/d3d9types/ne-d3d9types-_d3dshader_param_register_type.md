---
UID: NE:d3d9types._D3DSHADER_PARAM_REGISTER_TYPE
title: _D3DSHADER_PARAM_REGISTER_TYPE
author: windows-driver-content
description: Pixel and vertex shader operations specify register types in bits 28, 29, 30, 11, and 12 of destination and source parameter tokens.
old-location: display\shader_register_types.htm
old-project: display
ms.assetid: e1763ae1-5583-43fe-a342-3b9b5a92ef3f
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DSHADER_PARAM_REGISTER_TYPE, D3DSHADER_PARAM_REGISTER_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d9types.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DSHADER_PARAM_REGISTER_TYPE
req.alt-loc: d3d9types.h
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
req.typenames: D3DSHADER_PARAM_REGISTER_TYPE
---

# _D3DSHADER_PARAM_REGISTER_TYPE enumeration



## -description
Pixel and vertex shader operations specify register types in bits 28, 29, 30, 11, and 12 of destination and source parameter tokens. The following register types can be specified:



## -syntax

````
typedef enum _D3DSHADER_PARAM_REGISTER_TYPE { 
  D3DSPR_TEMP         = 0,
  D3DSPR_INPUT        = 1,
   D3DSPR_CONST       = 2,
  D3DSPR_ADDR         = 3,
  D3DSPR_TEXTURE      = 3,
  D3DSPR_RASTOUT      = 4,
  D3DSPR_ATTROUT      = 5,
  D3DSPR_TEXCRDOUT    = 6,
  D3DSPR_OUTPUT       = 6,
  D3DSPR_CONSTINT     = 7,
  D3DSPR_COLOROUT     = 8,
  D3DSPR_DEPTHOUT     = 9,
  D3DSPR_SAMPLER      = 10,
  D3DSPR_CONST2       = 11,
  D3DSPR_CONST3       = 12,
  D3DSPR_CONST4       = 13,
  D3DSPR_CONSTBOOL    = 14,
  D3DSPR_LOOP         = 15,
  D3DSPR_TEMPFLOAT16  = 16,
  D3DSPR_MISCTYPE     = 17,
  D3DSPR_LABEL        = 18,
  D3DSPR_PREDICATE    = 19,
  D3DSPR_FORCE_DWORD  = 0x7fffffff
} D3DSHADER_PARAM_REGISTER_TYPE;
````


## -enum-fields

### -field D3DSPR_TEMP

Temporary register file.


### -field D3DSPR_INPUT

Input register file.


### -field  D3DSPR_CONST

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

For &amp;lt; VS 3_0, texture coordinate output register file. For &amp;gt;/= VS 3_0, output register file. For PS, reserved.


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


## -remarks
