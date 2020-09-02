---
UID: NS:d3dumddi._DXVADDI_PROCAMPVALUES
title: _DXVADDI_PROCAMPVALUES (d3dumddi.h)
description: The DXVADDI_PROCAMPVALUES structure describes the ProcAmp control adjustment values.
old-location: display\dxvaddi_procampvalues.htm
tech.root: display
ms.assetid: bce6931d-af45-42aa-9be2-ded07f98c300
ms.date: 05/10/2018
keywords: ["DXVADDI_PROCAMPVALUES structure"]
ms.keywords: DXVA2_Structs_b731e88e-8f64-4199-9f75-9b5cba380aa8.xml, DXVADDI_PROCAMPVALUES, DXVADDI_PROCAMPVALUES structure [Display Devices], _DXVADDI_PROCAMPVALUES, d3dumddi/DXVADDI_PROCAMPVALUES, display.dxvaddi_procampvalues
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
req.typenames: DXVADDI_PROCAMPVALUES
f1_keywords:
 - _DXVADDI_PROCAMPVALUES
 - d3dumddi/_DXVADDI_PROCAMPVALUES
 - DXVADDI_PROCAMPVALUES
 - d3dumddi/DXVADDI_PROCAMPVALUES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - DXVADDI_PROCAMPVALUES
---

# _DXVADDI_PROCAMPVALUES structure


## -description

The DXVADDI_PROCAMPVALUES structure describes the ProcAmp control adjustment values.

## -struct-fields

### -field Brightness

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_fixed32">DXVADDI_FIXED32</a> structure that specifies the brightness of the output image, as it is written to the destination surface.

### -field Contrast

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_fixed32">DXVADDI_FIXED32</a> structure that specifies the contrast of the output image, as it is written to the destination surface.

### -field Hue

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_fixed32">DXVADDI_FIXED32</a> structure that specifies the hue of the output image, as it is written to the destination surface.

### -field Saturation

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_fixed32">DXVADDI_FIXED32</a> structure that specifies the saturation of the output image, as it is written to the destination surface.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_videoprocessblt">D3DDDIARG_VIDEOPROCESSBLT</a>

