---
UID: NS:d3dukmdt._D3DDDI_GAMMA_RAMP_DXGI_1
title: _D3DDDI_GAMMA_RAMP_DXGI_1 (d3dukmdt.h)
description: The D3DDDI_GAMMA_RAMP_DXGI_1 structure describes a gamma function.
old-location: display\d3dddi_gamma_ramp_dxgi_1.htm
tech.root: display
ms.assetid: f5c67404-3baf-44f1-8b19-f099cf71c178
ms.date: 05/10/2018
ms.keywords: D3DDDI_GAMMA_RAMP_DXGI_1, D3DDDI_GAMMA_RAMP_DXGI_1 structure [Display Devices], DmStructs_378e6432-010f-453c-8e59-d32f243543f0.xml, _D3DDDI_GAMMA_RAMP_DXGI_1, d3dukmdt/D3DDDI_GAMMA_RAMP_DXGI_1, display.d3dddi_gamma_ramp_dxgi_1
ms.topic: struct
f1_keywords:
 - "d3dukmdt/D3DDDI_GAMMA_RAMP_DXGI_1"
req.header: d3dukmdt.h
req.include-header: D3dukmdt.h
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
- d3dukmdt.h
api_name:
- D3DDDI_GAMMA_RAMP_DXGI_1
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_GAMMA_RAMP_DXGI_1
---

# _D3DDDI_GAMMA_RAMP_DXGI_1 structure


## -description


The D3DDDI_GAMMA_RAMP_DXGI_1 structure describes a gamma function.


## -struct-fields




### -field Scale

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dukmdt/ns-d3dukmdt-d3dddi_dxgi_rgb">D3DDDI_DXGI_RGB</a> structure that holds the scale for the gamma function.


### -field Offset

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dukmdt/ns-d3dukmdt-d3dddi_dxgi_rgb">D3DDDI_DXGI_RGB</a> structure that holds the offset for the gamma function.


### -field GammaCurve

An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dukmdt/ns-d3dukmdt-d3dddi_dxgi_rgb">D3DDDI_DXGI_RGB</a> structures that describe the curve of the gamma function.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dukmdt/ns-d3dukmdt-d3dddi_dxgi_rgb">D3DDDI_DXGI_RGB</a>
 

 

