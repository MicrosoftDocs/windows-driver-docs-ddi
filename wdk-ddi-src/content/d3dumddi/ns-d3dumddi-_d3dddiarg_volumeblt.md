---
UID: NS:d3dumddi._D3DDDIARG_VOLUMEBLT
title: _D3DDDIARG_VOLUMEBLT (d3dumddi.h)
description: The D3DDDIARG_VOLUMEBLT structure describes parameters for a volume bit-block transfer (bitblt) operation.
old-location: display\d3dddiarg_volumeblt.htm
tech.root: display
ms.assetid: 564afe6c-7a2e-4657-a481-24015c0be637
ms.date: 05/10/2018
keywords: ["D3DDDIARG_VOLUMEBLT structure"]
ms.keywords: D3DDDIARG_VOLUMEBLT, D3DDDIARG_VOLUMEBLT structure [Display Devices], UMDisplayDriver_param_Structs_21157114-7596-4031-8531-019e7acc3dbe.xml, _D3DDDIARG_VOLUMEBLT, d3dumddi/D3DDDIARG_VOLUMEBLT, display.d3dddiarg_volumeblt
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
req.typenames: D3DDDIARG_VOLUMEBLT
f1_keywords:
 - _D3DDDIARG_VOLUMEBLT
 - d3dumddi/_D3DDDIARG_VOLUMEBLT
 - D3DDDIARG_VOLUMEBLT
 - d3dumddi/D3DDDIARG_VOLUMEBLT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - D3DDDIARG_VOLUMEBLT
---

# _D3DDDIARG_VOLUMEBLT structure


## -description

The D3DDDIARG_VOLUMEBLT structure describes parameters for a volume bit-block transfer (bitblt) operation.

## -struct-fields

### -field hDstResource

[in] A handle to the destination surface.

### -field hSrcResource

[in] A handle to the source surface.

### -field DstX

[in] The width, in screen coordinates, of the destination volume in which the source volume is copied.

### -field DstY

[in] The height, in screen coordinates, of the destination volume in which the source volume is copied.

### -field DstZ

[in] The depth, in screen coordinates, of the destination volume in which the source volume is copied.

### -field SrcBox

[in] A D3DDDIBOX structure that describes the source volume texture to copy to the destination.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_volblt">VolBlt</a>