---
UID: NS:dxgiddi.DXGI_DDI_PRESENT_FLAGS
title: DXGI_DDI_PRESENT_FLAGS (dxgiddi.h)
description: Identifies how to perform a present operation.
old-location: display\dxgi_ddi_present_flags.htm
tech.root: display
ms.assetid: 87f3b66a-0fcb-4325-ae23-7f89d6b389e6
ms.date: 05/10/2018
ms.keywords: DXGI_DDI_PRESENT_FLAGS, DXGI_DDI_PRESENT_FLAGS structure [Display Devices], UMDisplayDriver_Dx10param_Structs_75234d4d-acce-4f1f-804c-f7128d885c2f.xml, display.dxgi_ddi_present_flags, dxgiddi/DXGI_DDI_PRESENT_FLAGS
ms.topic: struct
f1_keywords:
 - "dxgiddi/DXGI_DDI_PRESENT_FLAGS"
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
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
- dxgiddi.h
api_name:
- DXGI_DDI_PRESENT_FLAGS
product:
- Windows
targetos: Windows
req.typenames: DXGI_DDI_PRESENT_FLAGS
dev_langs:
 - c++
ms.custom: 19H1
---

# DXGI_DDI_PRESENT_FLAGS structure


## -description


Identifies how to perform a present operation.


## -struct-fields




### -field Blt

Specifies whether to perform a bit-block transfer (bitblt) data to the primary surface. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Flip

Specifies whether to flip to a new surface. 

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field PreferRight

Supported in Windows 8 and later versions.

Specifies that, if a stereo present operation must be reduced to mono, the present operation should show the view from the right eye.

If this member is not set, the default mono present operation shows the view from the left eye.

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).


### -field TemporaryMono

Supported in Windows 8 and later versions.

Specifies that  a present operation should use the left buffer as a mono (non-stereo) buffer.

Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).


### -field AllowTearing




### -field AllowFlexibleRefresh

 
### -field NoScanoutTransform

Supported in Windows 10, version 1901 and later.

This flag will only be passed if the driver set the D3DWDDM2_6DDI_SCANOUT_FLAG_TRANSFORMATION_DESIRED flag, instead of the D3DWDDM2_6DDI_SCANOUT_FLAG_TRANSFORMATION_REQUIRED flag of the [D3DWDDM2_6DDI_SCANOUT_FLAGS](../d3d10umddi/ne-d3d10umddi-d3dwddm2_6ddi_scanout_flags.md) enumeration.

### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 28 bits (0xFFFFFFF0) of the 32-bit <b>Value</b> member to zeros.


### -field Value

A member in the union that is contained in DXGI_DDI_PRESENT_FLAGS that can hold one 32-bit value that identifies how to perform a present operation.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_present">DXGI_DDI_ARG_PRESENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">PresentDXGI</a>
 

 

