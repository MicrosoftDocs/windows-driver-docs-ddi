---
UID: NE:d3d10umddi.D3D11_1_DDI_LOGIC_OP
title: D3D11_1_DDI_LOGIC_OP (d3d10umddi.h)
description: Indicates shader logic operations used in a blend state.
old-location: display\d3d11_1_ddi_logic_op.htm
ms.date: 04/01/2021
keywords: ["D3D11_1_DDI_LOGIC_OP enumeration"]
ms.keywords: D3D11_1_DDI_LOGIC_OP, D3D11_1_DDI_LOGIC_OP enumeration [Display Devices], D3D11_1_DDI_LOGIC_OP_AND, D3D11_1_DDI_LOGIC_OP_AND_INVERTED, D3D11_1_DDI_LOGIC_OP_AND_REVERSE, D3D11_1_DDI_LOGIC_OP_CLEAR, D3D11_1_DDI_LOGIC_OP_COPY, D3D11_1_DDI_LOGIC_OP_COPY_INVERTED, D3D11_1_DDI_LOGIC_OP_EQUIV, D3D11_1_DDI_LOGIC_OP_INVERT, D3D11_1_DDI_LOGIC_OP_NAND, D3D11_1_DDI_LOGIC_OP_NOOP, D3D11_1_DDI_LOGIC_OP_NOR, D3D11_1_DDI_LOGIC_OP_OR, D3D11_1_DDI_LOGIC_OP_OR_INVERTED, D3D11_1_DDI_LOGIC_OP_OR_REVERSE, D3D11_1_DDI_LOGIC_OP_SET, D3D11_1_DDI_LOGIC_OP_XOR, d3d10umddi/D3D11_1_DDI_LOGIC_OP, d3d10umddi/D3D11_1_DDI_LOGIC_OP_AND, d3d10umddi/D3D11_1_DDI_LOGIC_OP_AND_INVERTED, d3d10umddi/D3D11_1_DDI_LOGIC_OP_AND_REVERSE, d3d10umddi/D3D11_1_DDI_LOGIC_OP_CLEAR, d3d10umddi/D3D11_1_DDI_LOGIC_OP_COPY, d3d10umddi/D3D11_1_DDI_LOGIC_OP_COPY_INVERTED, d3d10umddi/D3D11_1_DDI_LOGIC_OP_EQUIV, d3d10umddi/D3D11_1_DDI_LOGIC_OP_INVERT, d3d10umddi/D3D11_1_DDI_LOGIC_OP_NAND, d3d10umddi/D3D11_1_DDI_LOGIC_OP_NOOP, d3d10umddi/D3D11_1_DDI_LOGIC_OP_NOR, d3d10umddi/D3D11_1_DDI_LOGIC_OP_OR, d3d10umddi/D3D11_1_DDI_LOGIC_OP_OR_INVERTED, d3d10umddi/D3D11_1_DDI_LOGIC_OP_OR_REVERSE, d3d10umddi/D3D11_1_DDI_LOGIC_OP_SET, d3d10umddi/D3D11_1_DDI_LOGIC_OP_XOR, display.d3d11_1_ddi_logic_op
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
targetos: Windows
tech.root: display
req.typenames: D3D11_1_DDI_LOGIC_OP
f1_keywords:
 - D3D11_1_DDI_LOGIC_OP
 - d3d10umddi/D3D11_1_DDI_LOGIC_OP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d10umddi.h
api_name:
 - D3D11_1_DDI_LOGIC_OP
---

# D3D11_1_DDI_LOGIC_OP enumeration

## -description

Indicates shader logic operations used in a blend state. In the following notation, the output value of each logic operation is given in terms of these values:

* *s* is the pixel shader output
* *d* is the contents of the render target view (RTV)

## -enum-fields

### -field D3D11_1_DDI_LOGIC_OP_CLEAR

0

### -field D3D11_1_DDI_LOGIC_OP_SET

1

### -field D3D11_1_DDI_LOGIC_OP_COPY

*s*

### -field D3D11_1_DDI_LOGIC_OP_COPY_INVERTED

~*s*

### -field D3D11_1_DDI_LOGIC_OP_NOOP

*d*

### -field D3D11_1_DDI_LOGIC_OP_INVERT

~*d*

### -field D3D11_1_DDI_LOGIC_OP_AND

*s* AND *d*

### -field D3D11_1_DDI_LOGIC_OP_NAND

~(*s* AND *d*)

### -field D3D11_1_DDI_LOGIC_OP_OR

*s* OR *d*

### -field D3D11_1_DDI_LOGIC_OP_NOR

~(*s* OR *d*)

### -field D3D11_1_DDI_LOGIC_OP_XOR

*s* ^ *d*

### -field D3D11_1_DDI_LOGIC_OP_EQUIV

~(*s* ^ *d*)

### -field D3D11_1_DDI_LOGIC_OP_AND_REVERSE

*s* AND ~*d*

### -field D3D11_1_DDI_LOGIC_OP_AND_INVERTED

~*s* AND *d*

### -field D3D11_1_DDI_LOGIC_OP_OR_REVERSE

*s* OR ~*d*

### -field D3D11_1_DDI_LOGIC_OP_OR_INVERTED

~*s* OR *d*

## -remarks

The **D3D11_1_DDI_LOGIC_OP** blend state  logic operations are specified by the [**D3D11_1_DDI_BLEND_DESC**](ns-d3d10umddi-d3d11_1_ddi_blend_desc.md).**LogicOp** member in a call to the [**CreateBlendState(D3D11_1)**](nc-d3d10umddi-pfnd3d11_1ddi_createblendstate.md) function.

## -see-also

[**CreateBlendState(D3D11_1)**](nc-d3d10umddi-pfnd3d11_1ddi_createblendstate.md)

[**D3D11_1_DDI_BLEND_DESC**](ns-d3d10umddi-d3d11_1_ddi_blend_desc.md)
