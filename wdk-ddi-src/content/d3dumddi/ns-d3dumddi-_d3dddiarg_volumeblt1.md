---
UID: NS:d3dumddi._D3DDDIARG_VOLUMEBLT1
title: _D3DDDIARG_VOLUMEBLT1 (d3dumddi.h)
description: Describes parameters for a volume bit-block transfer (bitblt) operation.
old-location: display\d3dddiarg_volumeblt1.htm
tech.root: display
ms.assetid: 685aad54-03f5-4e3c-83a7-a44745acc4fb
ms.date: 05/10/2018
keywords: ["D3DDDIARG_VOLUMEBLT1 structure"]
ms.keywords: D3DDDIARG_VOLUMEBLT1, D3DDDIARG_VOLUMEBLT1 structure [Display Devices], _D3DDDIARG_VOLUMEBLT1, d3dumddi/D3DDDIARG_VOLUMEBLT1, display.d3dddiarg_volumeblt1
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
req.typenames: D3DDDIARG_VOLUMEBLT1
f1_keywords:
 - _D3DDDIARG_VOLUMEBLT1
 - d3dumddi/_D3DDDIARG_VOLUMEBLT1
 - D3DDDIARG_VOLUMEBLT1
 - d3dumddi/D3DDDIARG_VOLUMEBLT1
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dumddi.h
api_name:
 - D3DDDIARG_VOLUMEBLT1
---

# _D3DDDIARG_VOLUMEBLT1 structure


## -description

Describes parameters for a volume bit-block transfer (bitblt) operation.

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

[in] A <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddibox">D3DDDIBOX</a> structure that describes the source volume texture to copy to the destination.

### -field CopyFlags

A value that specifies characteristics of a copy operation as a bitwise OR of the values in the <a href="/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-d3dddi_copy_flags">D3DDDI_COPY_FLAGS</a> enumeration type.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddibox">D3DDDIBOX</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-d3dddi_copy_flags">D3DDDI_COPY_FLAGS</a>