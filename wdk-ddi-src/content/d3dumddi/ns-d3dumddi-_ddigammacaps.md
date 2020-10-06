---
UID: NS:d3dumddi._DDIGAMMACAPS
title: _DDIGAMMACAPS (d3dumddi.h)
description: The DDIGAMMACAPS structure describes gamma-ramp capabilities that the user-mode display driver supports.
old-location: display\ddigammacaps.htm
tech.root: display
ms.assetid: 4db605f8-a1ed-4b75-8c72-f4846ae7007e
ms.date: 05/10/2018
keywords: ["DDIGAMMACAPS structure"]
ms.keywords: D3D_other_Structs_7aa0b131-f7e5-4208-b3bb-7a35fa0d5ef1.xml, DDIGAMMACAPS, DDIGAMMACAPS structure [Display Devices], _DDIGAMMACAPS, d3dumddi/DDIGAMMACAPS, display.ddigammacaps
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
req.typenames: DDIGAMMACAPS
f1_keywords:
 - _DDIGAMMACAPS
 - d3dumddi/_DDIGAMMACAPS
 - DDIGAMMACAPS
 - d3dumddi/DDIGAMMACAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - DDIGAMMACAPS
---

# _DDIGAMMACAPS structure


## -description

The DDIGAMMACAPS structure describes gamma-ramp capabilities that the user-mode display driver supports.

## -struct-fields

### -field GammaCaps

[out] A valid bitwise OR of the following capability bits that the driver supports.

| **Capability bit** | **Meaning** | 
|:--|:--|
| GAMMA_CAP_RGB256x3x16 (0x00000001) | Gamma-ramp data is stored as 256 16-bit RGB values. |

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_getcaps">D3DDDIARG_GETCAPS</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-_d3dddicaps_type">D3DDDICAPS_TYPE</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a>