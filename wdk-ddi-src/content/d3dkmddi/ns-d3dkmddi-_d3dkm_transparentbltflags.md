---
UID: NS:d3dkmddi._D3DKM_TRANSPARENTBLTFLAGS
title: D3DKM_TRANSPARENTBLTFLAGS (d3dkmddi.h)
description: Learn more about the D3DKM_TRANSPARENTBLTFLAGS structure.
ms.date: 06/09/2023
keywords: ["D3DKM_TRANSPARENTBLTFLAGS structure"]
ms.keywords: D3DKM_TRANSPARENTBLTFLAGS, D3DKM_TRANSPARENTBLTFLAGS structure [Display Devices], DmStructs_7190815e-5610-4c97-823f-8bdaae16c005.xml, _D3DKM_TRANSPARENTBLTFLAGS, d3dkmddi/D3DKM_TRANSPARENTBLTFLAGS, display.d3dkm_transparentbltflags
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 7
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
req.typenames: D3DKM_TRANSPARENTBLTFLAGS
f1_keywords:
 - _D3DKM_TRANSPARENTBLTFLAGS
 - d3dkmddi/_D3DKM_TRANSPARENTBLTFLAGS
 - D3DKM_TRANSPARENTBLTFLAGS
 - d3dkmddi/D3DKM_TRANSPARENTBLTFLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _D3DKM_TRANSPARENTBLTFLAGS
 - D3DKM_TRANSPARENTBLTFLAGS
---

# D3DKM_TRANSPARENTBLTFLAGS structure

## -description

The **D3DKM_TRANSPARENTBLTFLAGS** structure specifies the display adapter's ability to perform a hardware-accelerated bit-block transfer (bitblt) with transparency.

## -struct-fields

### -field HonorAlpha [in]

A UINT value that specifies in a hardware-accelerated transparent bit-block transfer whether the alpha channel should be used during comparison. **HonorAlpha** can be one of the following values.

| Value | Meaning |
| ----- | ------- |
| 1 | The display adapter does not ignore the alpha channel when it compares the reference color with the source color. |
| 0 | The display adapter ignores the alpha channel when it compares the reference color with the source color. |

Setting this member is equivalent to setting the first bit of the 32-bit **Value** member (0x00000001).

### -field Value [in]

A member in the union that D3DKM_TRANSPARENTBLTFLAGS contains. This member can hold a 32-bit value that specifies the display adapter's ability to perform hardware-accelerated bit-block transfer with transparency.

## -see-also

[**DXGK_GDIARG_TRANSPARENTBLT**](ns-d3dkmddi-_dxgk_gdiarg_transparentblt.md)
