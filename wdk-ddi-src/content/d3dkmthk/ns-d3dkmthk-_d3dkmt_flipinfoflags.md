---
UID: NS:d3dkmthk._D3DKMT_FLIPINFOFLAGS
title: _D3DKMT_FLIPINFOFLAGS (d3dkmthk.h)
description: The D3DKMT_FLIPINFOFLAGS structure identifies flipping capabilities of the display miniport driver that the OpenGL installable client driver (ICD) obtains by calling the D3DKMTQueryAdapterInfo function.
old-location: display\d3dkmt_flipinfoflags.htm
ms.date: 05/10/2018
keywords: ["D3DKMT_FLIPINFOFLAGS structure"]
ms.keywords: D3DKMT_FLIPINFOFLAGS, D3DKMT_FLIPINFOFLAGS structure [Display Devices], OpenGL_Structs_2e8d2e1b-7ae8-4ac4-916d-5cace7ef043e.xml, _D3DKMT_FLIPINFOFLAGS, d3dkmthk/D3DKMT_FLIPINFOFLAGS, display.d3dkmt_flipinfoflags
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
tech.root: display
req.typenames: D3DKMT_FLIPINFOFLAGS
f1_keywords:
 - _D3DKMT_FLIPINFOFLAGS
 - d3dkmthk/_D3DKMT_FLIPINFOFLAGS
 - D3DKMT_FLIPINFOFLAGS
 - d3dkmthk/D3DKMT_FLIPINFOFLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_FLIPINFOFLAGS
 - D3DKMT_FLIPINFOFLAGS
---

# _D3DKMT_FLIPINFOFLAGS structure


## -description

The D3DKMT_FLIPINFOFLAGS structure identifies flipping capabilities of the display miniport driver that the OpenGL installable client driver (ICD) obtains by calling the <a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtqueryadapterinfo">D3DKMTQueryAdapterInfo</a> function.

## -struct-fields

### -field FlipInterval

A UINT value that specifies whether the display miniport driver natively supports the scheduling of a flip command to take effect after two, three or four vertical syncs occur. Regardless of whether the display miniport driver supports a flip interval of two or greater, the driver must support an immediate flip and a flip interval of one.

Setting this member is equivalent to setting the first bit of a 32-bit value (0x00000001).

### -field Reserved

This member is reserved and should be set to zero. Setting this member is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of a 32-bit value to zeros.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtqueryadapterinfo">D3DKMTQueryAdapterInfo</a>



<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_flipqueueinfo">D3DKMT_FLIPQUEUEINFO</a>



<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_queryadapterinfo">D3DKMT_QUERYADAPTERINFO</a>

