---
UID: NS:d3dumddi._D3DDDIARG_BLT
title: _D3DDDIARG_BLT (d3dumddi.h)
description: The D3DDDIARG_BLT structure describes the parameters of a bit-block transfer (bitblt).
old-location: display\d3dddiarg_blt.htm
tech.root: display
ms.assetid: 9663d0fe-7397-49d7-b860-e466a9311aca
ms.date: 05/10/2018
keywords: ["D3DDDIARG_BLT structure"]
ms.keywords: D3DDDIARG_BLT, D3DDDIARG_BLT structure [Display Devices], UMDisplayDriver_param_Structs_1c7d23e1-c05e-42b6-802e-4a69a80006c8.xml, _D3DDDIARG_BLT, d3dumddi/D3DDDIARG_BLT, display.d3dddiarg_blt
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
req.typenames: D3DDDIARG_BLT
f1_keywords:
 - _D3DDDIARG_BLT
 - d3dumddi/_D3DDDIARG_BLT
 - D3DDDIARG_BLT
 - d3dumddi/D3DDDIARG_BLT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - D3DDDIARG_BLT
---

# _D3DDDIARG_BLT structure


## -description

The D3DDDIARG_BLT structure describes the parameters of a bit-block transfer (bitblt).

## -struct-fields

### -field hSrcResource

[in] A handle to the source resource.

### -field SrcSubResourceIndex

[in] The index to the source surface within the resource.

### -field SrcRect

[in] A <a href="/windows/win32/api/windef/ns-windef-tagrect">RECT</a> structure for the source rectangle.

### -field hDstResource

[in] A handle to the destination resource.

### -field DstSubResourceIndex

[in] The index to the destination surface within the resource.

### -field DstRect

[in] A <a href="/windows/win32/api/windef/ns-windef-tagrect">RECT</a> structure for the destination rectangle.

### -field ColorKey

[in] A value for the color key. Note that the <b>SrcColorKey</b> and <b>DstColorKey</b> bit-field flags are never set simultaneously in the <b>Flags</b> member.

### -field Flags

[in] A <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_bltflags">D3DDDI_BLTFLAGS</a> structure that identifies the type of bitblt to perform. Note that some bit-field flags in this structure are mutually exclusive with other flags. For more information about these flags, see the following Remarks section.

## -remarks

If a filtering option (for example, the <b>Point</b> or <b>Linear</b> bit-field flag) is not specified in the <b>Flags</b> member, the driver can use its own filtering technique.

The <b>SrcColorKey</b> and <b>DstColorKey</b> bit-field flags are never set simultaneously. Similarly, the <b>Point</b> bit-field flag is not simultaneously set with the <b>Linear</b> bit-field flag.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_blt">Blt</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_bltflags">D3DDDI_BLTFLAGS</a>



<a href="/windows/win32/api/windef/ns-windef-tagrect">RECT</a>