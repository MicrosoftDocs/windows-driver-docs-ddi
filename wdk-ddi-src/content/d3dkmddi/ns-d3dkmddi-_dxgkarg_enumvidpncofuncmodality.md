---
UID: NS:d3dkmddi._DXGKARG_ENUMVIDPNCOFUNCMODALITY
title: _DXGKARG_ENUMVIDPNCOFUNCMODALITY (d3dkmddi.h)
description: The DXGKARG_ENUMVIDPNCOFUNCMODALITY structure contains arguments for the DxgkDdiEnumVidPnCofuncModality function.
old-location: display\dxgkarg_enumvidpncofuncmodality.htm
ms.assetid: a67c9e20-68bf-45d5-bbf0-d324643b2a5d
ms.date: 05/10/2018
keywords: ["DXGKARG_ENUMVIDPNCOFUNCMODALITY structure"]
ms.keywords: DXGKARG_ENUMVIDPNCOFUNCMODALITY, DXGKARG_ENUMVIDPNCOFUNCMODALITY structure [Display Devices], DmStructs_7b6ad975-cf77-450d-9190-f74711cafe71.xml, _DXGKARG_ENUMVIDPNCOFUNCMODALITY, d3dkmddi/DXGKARG_ENUMVIDPNCOFUNCMODALITY, display.dxgkarg_enumvidpncofuncmodality
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
req.typenames: DXGKARG_ENUMVIDPNCOFUNCMODALITY
f1_keywords:
 - _DXGKARG_ENUMVIDPNCOFUNCMODALITY
 - d3dkmddi/_DXGKARG_ENUMVIDPNCOFUNCMODALITY
 - DXGKARG_ENUMVIDPNCOFUNCMODALITY
 - d3dkmddi/DXGKARG_ENUMVIDPNCOFUNCMODALITY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGKARG_ENUMVIDPNCOFUNCMODALITY
---

# _DXGKARG_ENUMVIDPNCOFUNCMODALITY structure


## -description

The DXGKARG_ENUMVIDPNCOFUNCMODALITY structure contains arguments for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality">DxgkDdiEnumVidPnCofuncModality</a> function. The <i>DxgkDdiEnumVidPnCofuncModality</i> function makes the source and target mode sets of a VidPN cofunctional with the VidPN's topology and the modes that have already been pinned.

## -struct-fields

### -field hConstrainingVidPn

A handle to the VidPn object for which the cofunctional modes are being requested.

### -field EnumPivotType

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_d3dkmdt_enumcofuncmodality_pivot_type">D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE</a> enumerator that supplies the enumeration pivot type.

### -field EnumPivot

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_enum_pivot">DXGK_ENUM_PIVOT</a> structure.

## -remarks

If a particular video present source or target is designated as the pivot of the enumeration, then <i>DxgkDdiEnumVidPnCofuncModality</i> must not change the mode set for that source or target.

The D3DKMDT_HVIDPN data type is defined in <i>D3dkmdt.h</i>. The D3DDDI_VIDEO_PRESENT_SOURCE_ID and D3DDDI_VIDEO_PRESENT_TARGET_ID data types are defined in <i>D3dukmdt.h</i>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_d3dkmdt_enumcofuncmodality_pivot_type">D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_enum_pivot">DXGK_ENUM_PIVOT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality">DxgkDdiEnumVidPnCofuncModality</a>

