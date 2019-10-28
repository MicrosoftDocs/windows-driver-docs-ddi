---
UID: NS:d3dkmddi._DXGK_ENUM_PIVOT
title: _DXGK_ENUM_PIVOT (d3dkmddi.h)
description: The DXGK_ENUM_PIVOT structure identifies either a video present source or a video present target as the enumeration pivot in a call to DxgkDdiEnumVidPnCofuncModality.
old-location: display\dxgk_enum_pivot.htm
ms.assetid: f2a234f3-aec9-4fe5-b720-bed9747d5a7f
ms.date: 05/10/2018
ms.keywords: DXGK_ENUM_PIVOT, DXGK_ENUM_PIVOT structure [Display Devices], DmStructs_7a6fa02d-2223-4052-9911-cf9be1ab931a.xml, _DXGK_ENUM_PIVOT, d3dkmddi/DXGK_ENUM_PIVOT, display.dxgk_enum_pivot
ms.topic: struct
f1_keywords:
 - "d3dkmddi/DXGK_ENUM_PIVOT"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- DXGK_ENUM_PIVOT
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_ENUM_PIVOT
---

# _DXGK_ENUM_PIVOT structure


## -description


The DXGK_ENUM_PIVOT structure identifies either a video present source or a video present target as the enumeration pivot in a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality">DxgkDdiEnumVidPnCofuncModality</a>. 


## -struct-fields




### -field VidPnSourceId

If the pivot of the enumeration is a video present source, this member is the identifier of that source.


### -field VidPnTargetId

If the pivot of the enumeration is a video present target, this member is the identifier of that target.


## -remarks



The <b>EnumPivot</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_enumvidpncofuncmodality">DXGKARG_ENUMVIDPNCOFUNCMODALITY</a> structure is a DXGK_ENUM_PIVOT structure. 

The <b>EnumPivotType</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_enumvidpncofuncmodality">DXGKARG_ENUMVIDPNCOFUNCMODALITY</a> structure is a value from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_d3dkmdt_enumcofuncmodality_pivot_type">D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE</a> enumeration that specifies the pivot type (for example, video present source, video present target, rotation transformation, or scaling transformation).



