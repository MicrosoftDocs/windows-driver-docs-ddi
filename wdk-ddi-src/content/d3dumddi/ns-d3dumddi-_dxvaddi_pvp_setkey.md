---
UID: NS:d3dumddi._DXVADDI_PVP_SETKEY
title: _DXVADDI_PVP_SETKEY (d3dumddi.h)
description: The DXVADDI_PVP_SETKEY structure describes a key that the decode device uses to start decoding a frame.
old-location: display\dxvaddi_pvp_setkey.htm
tech.root: display
ms.assetid: 3707f9c9-109e-4ac2-bc34-c9f4f7651306
ms.date: 05/10/2018
keywords: ["DXVADDI_PVP_SETKEY structure"]
ms.keywords: DXVA2_Structs_fbd26ed2-13ce-4f15-a7de-544f6f5fac33.xml, DXVADDI_PVP_SETKEY, DXVADDI_PVP_SETKEY structure [Display Devices], _DXVADDI_PVP_SETKEY, d3dumddi/DXVADDI_PVP_SETKEY, display.dxvaddi_pvp_setkey
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
req.typenames: DXVADDI_PVP_SETKEY
f1_keywords:
 - _DXVADDI_PVP_SETKEY
 - d3dumddi/_DXVADDI_PVP_SETKEY
 - DXVADDI_PVP_SETKEY
 - d3dumddi/DXVADDI_PVP_SETKEY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - DXVADDI_PVP_SETKEY
---

# _DXVADDI_PVP_SETKEY structure


## -description

The DXVADDI_PVP_SETKEY structure describes a key that the decode device uses to start decoding a frame.

## -struct-fields

### -field ContentKey

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_pvp_block128">DXVADDI_PVP_KEY128</a> structure that contains the 128-bit key.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_decodebeginframe">D3DDDIARG_DECODEBEGINFRAME</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_pvp_block128">DXVADDI_PVP_KEY128</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_decodebeginframe">DecodeBeginFrame</a>

