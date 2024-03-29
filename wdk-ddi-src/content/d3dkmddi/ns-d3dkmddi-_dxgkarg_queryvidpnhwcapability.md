---
UID: NS:d3dkmddi._DXGKARG_QUERYVIDPNHWCAPABILITY
title: DXGKARG_QUERYVIDPNHWCAPABILITY (d3dkmddi.h)
description: Learn more about the DXGKARG_QUERYVIDPNHWCAPABILITY structure.
ms.date: 06/09/2023
keywords: ["DXGKARG_QUERYVIDPNHWCAPABILITY structure"]
ms.keywords: "*INOUT_PDXGKARG_QUERYVIDPNHWCAPABILITY, DXGKARG_QUERYVIDPNHWCAPABILITY, DXGKARG_QUERYVIDPNHWCAPABILITY structure [Display Devices], DXGKARG_QUERYVIDPNHWCAPABILITY;typedef __inout DXGKARG_QUERYVIDPNHWCAPABILITY* INOUT_PDXGKARG_QUERYVIDPNHWCAPABILITY, DXGKARG_QUERYVIDPNHWCAPABILITY;typedef __inout DXGKARG_QUERYVIDPNHWCAPABILITY* INOUT_PDXGKARG_QUERYVIDPNHWCAPABILITY structure [Display Devices], DmStructs_64808a07-769c-4f57-b1c8-84a676f596a3.xml, _DXGKARG_QUERYVIDPNHWCAPABILITY, d3dkmddi/DXGKARG_QUERYVIDPNHWCAPABILITY, display.dxgkarg_queryvidpnhwcapability"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 7
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
req.typenames: DXGKARG_QUERYVIDPNHWCAPABILITY
f1_keywords:
 - _DXGKARG_QUERYVIDPNHWCAPABILITY
 - d3dkmddi/_DXGKARG_QUERYVIDPNHWCAPABILITY
 - DXGKARG_QUERYVIDPNHWCAPABILITY
 - d3dkmddi/DXGKARG_QUERYVIDPNHWCAPABILITY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_QUERYVIDPNHWCAPABILITY
 - DXGKARG_QUERYVIDPNHWCAPABILITY
---

# DXGKARG_QUERYVIDPNHWCAPABILITY structure

## -description

The **DXGKARG_QUERYVIDPNHWCAPABILITY** structure is used by the display miniport driver to describe the hardware capabilities of a functional VidPN in response to a call to the [**DxgkDdiQueryVidPnHWCapability**](nc-d3dkmddi-dxgkddi_queryvidpnhwcapability.md) function.

## -struct-fields

### -field hFunctionalVidPn [in]

A handle to a functional VidPN object for which the hardware capabilities are being queried.

### -field SourceId [in]

An integer that identifies a video present source on the display adapter.

### -field TargetId [in]

An integer that identifies a video present target on the display adapter.

### -field VidPnHWCaps [out]

A [**D3DKMDT_VIDPN_HW_CAPABILITY**](../d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_hw_capability.md) structure that describes the capabilities of the display miniport driver to perform display operations without dedicated GPU hardware support.

## -remarks

The D3DDDI_VIDEO_PRESENT_SOURCE_ID and D3DDDI_VIDEO_PRESENT_TARGET_ID data types are defined in *D3dukmdt.h*.

Video present source identifiers are assigned by the operating system. [**DxgkDdiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md), implemented by the display miniport driver, returns the number N of video present sources supported by the display adapter. Then the operating system assigns identifiers 0, 1, 2, ... N - 1.

Video present target identifiers are assigned by the display miniport driver. [**DxgkDdiQueryChildRelations**](../dispmprt/nc-dispmprt-dxgkddi_query_child_relations.md), implemented by the display miniport driver, returns an array of [**DXGK_CHILD_DESCRIPTOR**](../dispmprt/ns-dispmprt-_dxgk_child_descriptor.md) structures, each of which contains an identifier.

For more information about video present sources and targets, see [Introduction to Video Present Networks](/windows-hardware/drivers/display/introduction-to-video-present-networks).

## -see-also

[**D3DKMDT_VIDEO_PRESENT_SOURCE**](../d3dkmdt/ns-d3dkmdt-_d3dkmdt_video_present_source.md)

[**D3DKMDT_VIDEO_PRESENT_TARGET**](../d3dkmdt/ns-d3dkmdt-_d3dkmdt_video_present_target.md)

[**D3DKMDT_VIDPN_HW_CAPABILITY**](../d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_hw_capability.md)

[**D3DKMDT_VIDPN_PRESENT_PATH**](../d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path.md)

[**DXGK_CHILD_DESCRIPTOR**](../dispmprt/ns-dispmprt-_dxgk_child_descriptor.md)

[**DxgkDdiQueryChildRelations**](../dispmprt/nc-dispmprt-dxgkddi_query_child_relations.md)

[**DxgkDdiQueryVidPnHWCapability**](nc-d3dkmddi-dxgkddi_queryvidpnhwcapability.md)

[**DxgkDdiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md)
