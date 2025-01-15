---
UID: NS:d3dkmddi._DXGK_QUERYINTEGRATEDDISPLAYOUT
tech.root: display
title: DXGK_QUERYINTEGRATEDDISPLAYOUT
ms.date: 01/13/2025
targetos: Windows
description: Learn more about the DXGK_QUERYINTEGRATEDDISPLAYOUT structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGK_QUERYINTEGRATEDDISPLAYOUT, *PDXGK_QUERYINTEGRATEDDISPLAYOUT
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_QUERYINTEGRATEDDISPLAYOUT
 - PDXGK_QUERYINTEGRATEDDISPLAYOUT
 - DXGK_QUERYINTEGRATEDDISPLAYOUT
f1_keywords:
 - _DXGK_QUERYINTEGRATEDDISPLAYOUT
 - d3dkmddi/_DXGK_QUERYINTEGRATEDDISPLAYOUT
 - PDXGK_QUERYINTEGRATEDDISPLAYOUT
 - d3dkmddi/PDXGK_QUERYINTEGRATEDDISPLAYOUT
 - DXGK_QUERYINTEGRATEDDISPLAYOUT
 - d3dkmddi/DXGK_QUERYINTEGRATEDDISPLAYOUT
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_QUERYINTEGRATEDDISPLAYOUT
---

## -description

The **DXGK_QUERYINTEGRATEDDISPLAYOUT** structure is used to output queried information for an integrated display.

## -struct-fields

### -field Flags

A [**DXGK_INTEGRATEDDISPLAYFLAGS**](ns-d3dkmddi-_dxgk_integrateddisplayflags.md) structure that contains flags describing properties of the integrated display.

### -field NativeTiming

A [**D3DKMDT_VIDEO_SIGNAL_INFO**](../d3dkmdt/ns-d3dkmdt-_d3dkmdt_video_signal_info.md) structure that contains information about a video signal driven by a video output on a display adapter.

### -field LinkCapabilities

A [**DXGK_MONITORLINKINFO_CAPABILITIES**](../d3dkmdt/ns-d3dkmdt-_dxgk_monitorlinkinfo_capabilities.md) structure with flags that describe capabilities for driving the monitor.

### -field Colorimetry

A [**DXGK_COLORIMETRY**](ns-d3dkmddi-_dxgk_colorimetry.md) enumeration that indicates the colorimetry support of the display.

### -field DisplayTechnology

A [**DXGK_DISPLAY_TECHNOLOGY**](../d3dkmdt/ne-d3dkmdt-_dxgk_display_technology.md) enumeration that describes the technology used by the display.

### -field IntendedUsage

A [**DXGK_DISPLAY_USAGE**](../d3dkmdt/ne-d3dkmdt-_dxgk_display_usage.md) enumeration that specifies the intended usage of the display.

### -field Instance

A BYTE value that uniquely identifies the instance of the integrated display being queried.

### -field DescriptorType

A [**DXGK_DISPLAY_DESCRIPTOR_TYPE**](../d3dkmdt/ne-d3dkmdt-_dxgk_display_descriptor_type.md) enumeration that specifies the display descriptor type in **Descriptor**.

### -field Descriptor[1]

A BYTE array that contains the descriptor data. The type and format of this data depend on the **DescriptorType**.

## -remarks

## -see-also

[**DXGK_QUERYADAPTERINFOTYPE**](../d3dkmddi/ne-d3dkmddi-_dxgk_queryadapterinfotype.md)

[**DXGKDDI_QUERYADAPTERINFO**](../d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo.md)
