---
UID: NS:d3dumddi._DDIMULTISAMPLEQUALITYLEVELSDATA
title: _DDIMULTISAMPLEQUALITYLEVELSDATA (d3dumddi.h)
description: The DDIMULTISAMPLEQUALITYLEVELSDATA structure describes the number of multiple-sample quality levels for a given render-target format.
old-location: display\ddimultisamplequalitylevelsdata.htm
tech.root: display
ms.assetid: 48eeea6a-6a1d-43f7-a74c-3ca896c7b2d4
ms.date: 05/10/2018
keywords: ["DDIMULTISAMPLEQUALITYLEVELSDATA structure"]
ms.keywords: D3D_other_Structs_a83f4a87-4963-41c8-9ef7-e1ce0b8843c5.xml, DDIMULTISAMPLEQUALITYLEVELSDATA, DDIMULTISAMPLEQUALITYLEVELSDATA structure [Display Devices], _DDIMULTISAMPLEQUALITYLEVELSDATA, d3dumddi/DDIMULTISAMPLEQUALITYLEVELSDATA, display.ddimultisamplequalitylevelsdata
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
req.typenames: DDIMULTISAMPLEQUALITYLEVELSDATA
f1_keywords:
 - _DDIMULTISAMPLEQUALITYLEVELSDATA
 - d3dumddi/_DDIMULTISAMPLEQUALITYLEVELSDATA
 - DDIMULTISAMPLEQUALITYLEVELSDATA
 - d3dumddi/DDIMULTISAMPLEQUALITYLEVELSDATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - DDIMULTISAMPLEQUALITYLEVELSDATA
---

# _DDIMULTISAMPLEQUALITYLEVELSDATA structure


## -description

The DDIMULTISAMPLEQUALITYLEVELSDATA structure describes the number of multiple-sample quality levels for a given render-target format.

## -struct-fields

### -field Format

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>-typed value that indicates the surface format of the multiple-sampled render target.

### -field Flip

[in] A Boolean value that specifies whether the resolution is flip or bit-block transfer (blt) style. <b>TRUE</b> indicates flip-style resolution; <b>FALSE</b> indicates blt-style resolution.

### -field MsType

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddimultisample_type">D3DDDIMULTISAMPLE_TYPE</a>-typed value that indicates the level of full-scene multiple sampling. If the display device supports maskable multiple sampling (that is, more than one sample for a multiple-sample render-target format plus antialias support), the user-mode display driver must provide the number of quality levels for the D3DDDIMULTISAMPLE_NONMASKABLE (1) value.

### -field QualityLevels

[in] The number of multiple-sample quality levels that the user-mode display driver supports for the render-target format that is specified by the <b>Format</b>, <b>bFlip</b>, and <b>MSType</b> members.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_getcaps">D3DDDIARG_GETCAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-_d3dddicaps_type">D3DDDICAPS_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddimultisample_type">D3DDDIMULTISAMPLE_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a>

