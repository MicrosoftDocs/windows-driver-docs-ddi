---
UID: NS:dxgiddi.DXGI_DDI_ARG_BLT_FLAGS
title: DXGI_DDI_ARG_BLT_FLAGS (dxgiddi.h)
description: The DXGI_DDI_ARG_BLT_FLAGS structure identifies the type of bit-block transfer (bitblt) to perform.
old-location: display\dxgi_ddi_arg_blt_flags.htm
tech.root: display
ms.assetid: 812679d2-b05c-4533-b4b2-01b973b0d80f
ms.date: 05/10/2018
keywords: ["DXGI_DDI_ARG_BLT_FLAGS structure"]
ms.keywords: DXGI_DDI_ARG_BLT_FLAGS, DXGI_DDI_ARG_BLT_FLAGS structure [Display Devices], UMDisplayDriver_Dx10param_Structs_22ccf0e7-83cc-443e-b4a1-c1a2f3bc24a0.xml, display.dxgi_ddi_arg_blt_flags, dxgiddi/DXGI_DDI_ARG_BLT_FLAGS
f1_keywords:
 - "dxgiddi/DXGI_DDI_ARG_BLT_FLAGS"
 - "DXGI_DDI_ARG_BLT_FLAGS"
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
- DXGI_DDI_ARG_BLT_FLAGS
product:
- Windows
targetos: Windows
req.typenames: DXGI_DDI_ARG_BLT_FLAGS
---

# DXGI_DDI_ARG_BLT_FLAGS structure


## -description


The DXGI_DDI_ARG_BLT_FLAGS structure identifies the type of bit-block transfer (bitblt) to perform.


## -struct-fields




### -field Resolve

A UINT value that specifies that the bitblt resolves multiple samples to one pixel. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Convert

A UINT value that specifies that the bitblt also performs a format conversion.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field Stretch

A UINT value that specifies that a stretching bitblt is performed.

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).


### -field Present

A UINT value that specifies that a presenting bitblt is performed.

Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 28 bits (0xFFFFFFF0) of the 32-bit <b>Value</b> member to zeros.


### -field Value

A member in the union that DXGI_DDI_ARG_BLT_FLAGS contains that can hold a 32-bit value that identifies the bitblt type. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_blt">DXGI_DDI_ARG_BLT</a>
 

 

