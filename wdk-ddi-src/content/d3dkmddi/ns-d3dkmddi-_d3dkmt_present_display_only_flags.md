---
UID: NS:d3dkmddi._D3DKMT_PRESENT_DISPLAY_ONLY_FLAGS
title: _D3DKMT_PRESENT_DISPLAY_ONLY_FLAGS (d3dkmddi.h)
description: Indicates how a kernel mode display-only driver (KMDOD) is to perform a present operation.
old-location: display\d3dkmt_present_display_only_flags.htm
ms.assetid: a45dfdeb-06d2-49c8-a6e1-f42a43857492
ms.date: 05/10/2018
keywords: ["_D3DKMT_PRESENT_DISPLAY_ONLY_FLAGS structure"]
ms.keywords: D3DKMT_PRESENT_DISPLAY_ONLY_FLAGS, D3DKMT_PRESENT_DISPLAY_ONLY_FLAGS structure [Display Devices], _D3DKMT_PRESENT_DISPLAY_ONLY_FLAGS, d3dkmddi/D3DKMT_PRESENT_DISPLAY_ONLY_FLAGS, display.d3dkmt_present_display_only_flags
f1_keywords:
 - "d3dkmddi/D3DKMT_PRESENT_DISPLAY_ONLY_FLAGS"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3dkmddi.h
api_name:
- D3DKMT_PRESENT_DISPLAY_ONLY_FLAGS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_PRESENT_DISPLAY_ONLY_FLAGS
---

# _D3DKMT_PRESENT_DISPLAY_ONLY_FLAGS structure


## -description


Indicates how a kernel mode display-only driver (KMDOD) is to perform a present operation.


## -struct-fields




### -field Rotate

[in] A UINT value that specifies whether to rotate the presentation data to match the current orientation of the screen during the presentation bit-block transfer (bitblt). The current orientation of the screen is set in the <b>Rotation</b> member of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path_transformation">D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION</a> structure, which is set in the <b>ContentTransformation</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path">D3DKMDT_VIDPN_PRESENT_PATH</a> structure for the video present path.

The KMDOD should rotate the data only if the <b>Rotate</b> bit-field flag is set. Even if the KMDOD determines that the current orientation of the screen is rotated from the presentation data and <b>Rotate</b> is not set, the KMDOD should not rotate the data.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Reserved

[in] This member is reserved and should be set to zero.

Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFF) of the 32-bit <b>Value</b> member to zeros.


### -field Value

A member in the union that <b>D3DKMT_PRESENT_DISPLAY_ONLY_FLAGS</b> contains that can hold a 32-bit value that identifies the type of present operation to perform.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path">D3DKMDT_VIDPN_PRESENT_PATH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path_transformation">D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION</a>
 

 

