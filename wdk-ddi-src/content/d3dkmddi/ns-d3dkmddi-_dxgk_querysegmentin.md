---
UID: NS:d3dkmddi._DXGK_QUERYSEGMENTIN
title: _DXGK_QUERYSEGMENTIN (d3dkmddi.h)
description: The DXGK_QUERYSEGMENTIN structure describes relevant information for a memory-segment query through a call to the display miniport driver's DxgkDdiQueryAdapterInfo function.
old-location: display\dxgk_querysegmentin.htm
ms.date: 05/10/2018
keywords: ["DXGK_QUERYSEGMENTIN structure"]
ms.keywords: DXGK_QUERYSEGMENTIN, DXGK_QUERYSEGMENTIN structure [Display Devices], DmStructs_d47cf13d-48ec-49fd-b80c-4df1501db329.xml, _DXGK_QUERYSEGMENTIN, d3dkmddi/DXGK_QUERYSEGMENTIN, display.dxgk_querysegmentin
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
req.typenames: DXGK_QUERYSEGMENTIN
f1_keywords:
 - _DXGK_QUERYSEGMENTIN
 - d3dkmddi/_DXGK_QUERYSEGMENTIN
 - DXGK_QUERYSEGMENTIN
 - d3dkmddi/DXGK_QUERYSEGMENTIN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGK_QUERYSEGMENTIN
---

# _DXGK_QUERYSEGMENTIN structure


## -description

The DXGK_QUERYSEGMENTIN structure describes relevant information for a memory-segment query through a call to the display miniport driver's <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a> function.

## -struct-fields

### -field AgpApertureBase

[in] A PHYSICAL_ADDRESS data type (which is defined as LARGE_INTEGER) that indicates the base address of the AGP aperture.

### -field AgpApertureSize

[in] A LARGE_INTEGER that indicates the size, in bytes, of the available AGP aperture.

### -field AgpFlags

[in] A <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_segmentflags">DXGK_SEGMENTFLAGS</a> structure that identifies properties for the available AGP aperture in bit-field flags.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryadapterinfo">DXGKARG_QUERYADAPTERINFO</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_querysegmentout">DXGK_QUERYSEGMENTOUT</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_segmentdescriptor">DXGK_SEGMENTDESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_segmentflags">DXGK_SEGMENTFLAGS</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a>
