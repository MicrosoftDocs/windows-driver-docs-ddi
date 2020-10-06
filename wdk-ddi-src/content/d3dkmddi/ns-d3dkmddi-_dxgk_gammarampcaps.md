---
UID: NS:d3dkmddi._DXGK_GAMMARAMPCAPS
title: _DXGK_GAMMARAMPCAPS (d3dkmddi.h)
description: The DXGK_GAMMARAMPCAPS structure identifies gamma-ramp capabilities of the display miniport driver that the driver provides through a call to its DxgkDdiQueryAdapterInfo function.
old-location: display\dxgk_gammarampcaps.htm
ms.assetid: 3e160700-5d90-4241-8ed4-8d87b545b9c3
ms.date: 05/10/2018
keywords: ["DXGK_GAMMARAMPCAPS structure"]
ms.keywords: DXGK_GAMMARAMPCAPS, DXGK_GAMMARAMPCAPS structure [Display Devices], DmStructs_2f60099d-a359-41f4-b3d0-a7c0d0a6cca4.xml, _DXGK_GAMMARAMPCAPS, d3dkmddi/DXGK_GAMMARAMPCAPS, display.dxgk_gammarampcaps
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.typenames: DXGK_GAMMARAMPCAPS
f1_keywords:
 - _DXGK_GAMMARAMPCAPS
 - d3dkmddi/_DXGK_GAMMARAMPCAPS
 - DXGK_GAMMARAMPCAPS
 - d3dkmddi/DXGK_GAMMARAMPCAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGK_GAMMARAMPCAPS
---

# _DXGK_GAMMARAMPCAPS structure


## -description

The DXGK_GAMMARAMPCAPS structure identifies gamma-ramp capabilities of the display miniport driver that the driver provides through a call to its <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a> function.

## -struct-fields

### -field Gamma_Rgb256x3x16

A UINT value that specifies whether gamma ramp data is stored as 256 16-bit RGB values. Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).

### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.

### -field Value

A member in the union that DXGK_GAMMARAMPCAPS contains that can hold a 32-bit value that identifies gamma-ramp capabilities.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryadapterinfo">DXGKARG_QUERYADAPTERINFO</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a>