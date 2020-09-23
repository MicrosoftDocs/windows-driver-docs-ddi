---
UID: NS:d3dkmddi._DXGKARG_QUERYVIDPNHWCAPABILITY
title: _DXGKARG_QUERYVIDPNHWCAPABILITY (d3dkmddi.h)
description: The DXGKARG_QUERYVIDPNHWCAPABILITY structure is used by the display miniport driver to describe the hardware capabilities of a functional VidPN in response to a call to the DxgkDdiQueryVidPnHWCapability function.
old-location: display\dxgkarg_queryvidpnhwcapability.htm
ms.assetid: b5f8073c-9989-4413-842d-e3e295cc3470
ms.date: 05/10/2018
keywords: ["DXGKARG_QUERYVIDPNHWCAPABILITY structure"]
ms.keywords: "*INOUT_PDXGKARG_QUERYVIDPNHWCAPABILITY, DXGKARG_QUERYVIDPNHWCAPABILITY, DXGKARG_QUERYVIDPNHWCAPABILITY structure [Display Devices], DXGKARG_QUERYVIDPNHWCAPABILITY;typedef __inout DXGKARG_QUERYVIDPNHWCAPABILITY* INOUT_PDXGKARG_QUERYVIDPNHWCAPABILITY, DXGKARG_QUERYVIDPNHWCAPABILITY;typedef __inout DXGKARG_QUERYVIDPNHWCAPABILITY* INOUT_PDXGKARG_QUERYVIDPNHWCAPABILITY structure [Display Devices], DmStructs_64808a07-769c-4f57-b1c8-84a676f596a3.xml, _DXGKARG_QUERYVIDPNHWCAPABILITY, d3dkmddi/DXGKARG_QUERYVIDPNHWCAPABILITY, display.dxgkarg_queryvidpnhwcapability"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
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
 - DXGKARG_QUERYVIDPNHWCAPABILITY;typedef __inout DXGKARG_QUERYVIDPNHWCAPABILITY* INOUT_PDXGKARG_QUERYVIDPNHWCAPABILITY
---

# _DXGKARG_QUERYVIDPNHWCAPABILITY structure


## -description

The DXGKARG_QUERYVIDPNHWCAPABILITY structure is used by the display miniport driver to describe the hardware capabilities of a functional VidPN in response to a call to the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryvidpnhwcapability">DxgkDdiQueryVidPnHWCapability</a> function.

## -struct-fields

### -field hFunctionalVidPn

[in] A handle to a functional VidPN object for which the hardware capabilities are being queried.

### -field SourceId

[in] An integer that identifies a video present source on the display adapter.

### -field TargetId

[in] An integer that identifies a video present target on the display adapter.

### -field VidPnHWCaps

[out] A <a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_hw_capability">D3DKMDT_VIDPN_HW_CAPABILITY</a> structure that describes the capabilities of the display miniport driver to perform display operations without dedicated GPU hardware support.

## -remarks

The D3DDDI_VIDEO_PRESENT_SOURCE_ID and D3DDDI_VIDEO_PRESENT_TARGET_ID data types are defined in <i>D3dukmdt.h</i>.

Video present source identifiers are assigned by the operating system. <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a>, implemented by the display miniport driver, returns the number N of video present sources supported by the display adapter. Then the operating system assigns identifiers 0, 1, 2, ... N - 1.

Video present target identifiers are assigned by the display miniport driver. <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_child_relations">DxgkDdiQueryChildRelations</a>, implemented by the display miniport driver, returns an array of <a href="/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_child_descriptor">DXGK_CHILD_DESCRIPTOR</a> structures, each of which contains an identifier.

For more information about video present sources and targets, see <a href="/windows-hardware/drivers/display/introduction-to-video-present-networks">Introduction to Video Present Networks</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_video_present_source">D3DKMDT_VIDEO_PRESENT_SOURCE</a>



<a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_video_present_target">D3DKMDT_VIDEO_PRESENT_TARGET</a>



<a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_hw_capability">D3DKMDT_VIDPN_HW_CAPABILITY</a>



<a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path">D3DKMDT_VIDPN_PRESENT_PATH</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_child_descriptor">DXGK_CHILD_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_child_relations">DxgkDdiQueryChildRelations</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryvidpnhwcapability">DxgkDdiQueryVidPnHWCapability</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a>