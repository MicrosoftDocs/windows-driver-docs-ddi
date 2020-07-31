---
UID: NS:d3dkmddi._DXGK_QUERYINTEGRATEDDISPLAYOUT2
title: _DXGK_QUERYINTEGRATEDDISPLAYOUT2 (d3dkmddi.h)
description: Used during a query for the integrated display output.
ms.assetid: f40c9cdf-92f4-40c4-b7c4-52109b8494ef
ms.date: 10/19/2018
keywords: ["_DXGK_QUERYINTEGRATEDDISPLAYOUT2 structure"]
f1_keywords:
 - "d3dkmddi/_DXGK_QUERYINTEGRATEDDISPLAYOUT2"
 - "_DXGK_QUERYINTEGRATEDDISPLAYOUT2"
ms.keywords: _DXGK_QUERYINTEGRATEDDISPLAYOUT2, DXGK_QUERYINTEGRATEDDISPLAYOUT2, *PDXGK_QUERYINTEGRATEDDISPLAYOUT2,
req.header: d3dkmddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DXGK_QUERYINTEGRATEDDISPLAYOUT2, *PDXGK_QUERYINTEGRATEDDISPLAYOUT2
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- _DXGK_QUERYINTEGRATEDDISPLAYOUT2
product: 
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: 19H1
---

# _DXGK_QUERYINTEGRATEDDISPLAYOUT2 structure

## -description

Used during a query for the integrated display output.

## -struct-fields

### -field Flags

[out] Pointer to a [DXGK_INTEGRATEDDISPLAYFLAGS](ns-d3dkmddi-_dxgk_integrateddisplayflags.md) structure that describes simple properties of an integrated display. Orientation values of 0 degrees indicate no override from the descriptor.

### -field NativeTiming

[out] Pointer to a [D3DKMDT_VIDEO_SIGNAL_INFO]/d3dkmdt/ns-d3dkmdt-_d3dkmdt_video_signal_info.md) structure that contains information about a native timing of the integrated display. Should be zeroed to indicate no override. This value overrides the native timing in the descriptor. Since the driver is responsible for providing the descriptor, the only expected usage of this override is to describe a timing which cannot be described by an EDID, most obviously, a display which has more than 4095 addressable pixels in either direction.
If a NativeTiming override is provided, the OS will not call [DxgkDdiRecommendMonitorModes](nc-d3dkmddi-dxgkddi_recommendmonitormodes.md) for this target. Generally, integrated panels do not support a large set of timings and the driver should be well matched to the EDID provided. If the driver needs to describe multiple overrides for monitor modes, it should leave the NativeTiming structure zeroed and report all the overrides using DxgkDdiRecommendMonitorModes.

### -field LinkCapabilities

[out] Pointer to a [DXGK_MONITORLINKINFO_CAPABILITIES](../d3dkmdt/ns-d3dkmdt-_dxgk_monitorlinkinfo_capabilities.md) structure that describes the link capabilities for driving the monitor. This is the same link capabilities as the OS would query from an external display after hot-plug. Since an integrated display is exposed during adapter driver initialization, the capabilities are described directly rather make an additional DDI call.

Starting in WDDM 2.6, this member is used to report synchronization support.

### -field Colorimetry

[out] Colorimetry related overrides for the display. See the description of [DXGK_COLORIMETRY](ns-d3dkmddi-_dxgk_colorimetry.md) for the field definitions and restrictions on the combinations of fields.

### -field DisplayTechnology

[out] Value that represents the technology of the display. Used to optimize experience, for example enabling a darker theme with reduced blue content on DXGK_DT_OLED displays.

### -field IntendedUsage

[out] Value that indicates the manufacturer’s intended usage of the display. The value reported should be DXGK_DU_GENERIC, unless the driver has information indicating a more specific usage. The expectation is that if the integrated display is intended to be used for AR, VR or auxiliary output, the driver would have to have enough specific handling that it would be able to report the correct usage.

### -field Instance

[out] A zero-based integer for the instance of integrated panel. Used to order multiple integrated panels. Values must be unique and contiguous across integrated targets but are not required to be reported in order.

### -field DescriptorType

[out] Value to indicate the type of descriptor. For WDDM 2.4 this value must be DXGK_DDT_EDID. From WDDM 2.5 and later, either DXGK_DDT_EDID or DXGK_DDT_DISPLAYID is allowed.

### -field DitheringSupport

[out] A [D3DKMDT_WIRE_FORMAT_AND_PREFERENCE](../d3dkmdt/ns-d3dkmdt-_d3dkmdt_wire_format_and_preference.md) field that contains the flags for each wire-format. The driver should set the wire-format bit for each format where the driver and hardware supports dithering beneficial to image quality when the source pixel format contains higher precision than the wire-format.

## -remarks

The fields provide overrides attributes of the display which could be provided by a descriptor, but either can't be described by an EDID or have commonly missing or incorrect in EDIDs. Where there is a conflict between the descriptor and these override fields, the OS will use the overrides when valid.

The OS will sanity check the fields and will fail driver start if any fields are found to be inconsistent or invalid. For most fields, sanity checking simply means verifying that reported values are in range but the Colorimetry, Instance and Descriptor fields have further validation applied. For Colorimetry, see the description of DXGK_COLORIMETRY for validation. Instance values are verified to be consistent across all integrated displays as noted above. The Descriptor must be a valid EDID.

## -see-also
