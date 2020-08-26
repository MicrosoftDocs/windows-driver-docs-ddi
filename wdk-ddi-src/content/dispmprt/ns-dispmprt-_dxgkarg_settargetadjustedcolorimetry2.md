---
UID: NS:dispmprt._DXGKARG_SETTARGETADJUSTEDCOLORIMETRY2
title: _DXGKARG_SETTARGETADJUSTEDCOLORIMETRY2 (dispmprt.h)
description: Arguments used in the DXGKDDI_SETTARGETADJUSTEDCOLORIMETRY2 callback function.
ms.assetid: 5d6faac0-b479-4a4b-8d10-6607607fa5d5
ms.date: 10/19/2018
keywords: ["DXGKARG_SETTARGETADJUSTEDCOLORIMETRY2 structure"]
f1_keywords:
 - "dispmprt/_DXGKARG_SETTARGETADJUSTEDCOLORIMETRY2"
 - "_DXGKARG_SETTARGETADJUSTEDCOLORIMETRY2"
ms.keywords: _DXGKARG_SETTARGETADJUSTEDCOLORIMETRY2, DXGKARG_SETTARGETADJUSTEDCOLORIMETRY2, *PDXGKARG_SETTARGETADJUSTEDCOLORIMETRY2, 
req.header: dispmprt.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DXGKARG_SETTARGETADJUSTEDCOLORIMETRY2, *PDXGKARG_SETTARGETADJUSTEDCOLORIMETRY2
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- dispmprt.h
api_name: 
- _DXGKARG_SETTARGETADJUSTEDCOLORIMETRY2
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# _DXGKARG_SETTARGETADJUSTEDCOLORIMETRY2 structure

## -description

Describes the colorimetry and SDR white level for a video present target. Used in the [DXGKDDI_SETTARGETADJUSTEDCOLORIMETRY2](nc-dispmprt-dxgkddi_settargetadjustedcolorimetry2.md) callback function.

## -struct-fields

### -field TargetId

The identifier of a display adapter's video present target.

### -field AdjustedColorimetry

A [DXGK_COLORIMETRY](../d3dkmddi/ns-d3dkmddi-_dxgk_colorimetry.md) structure containing the colorimetry related fields for the monitor attached to this target after the OS has processed the display device descriptor, all overrides and any adjustments.

### -field SdrWhiteLevel
 
This represents the SDR (standard dynamic range) white level value in nits for all SDR content displayed to the video present target.

The OS assumes that all SDR content it is given is at 80 nits and by default this white level is appropriate.

The user may request that the OS boost the white level of all SDR content.  When a boost is applied, the OS and the driver are responsible for boosting all SDR content appropriately when the white level is not set at 80 nits.

The driver is responsible for boosting the hardware cursor when it is in use.

This adjustment should be applied as follows:

```cpp
RGBout = RGBin * (SDRWhiteLevel / 80);
```

The driver is also potentially responsible for boosting the contents of an SDR MPO (multi-plane overlay) plane. The driver should use the SDR white level given by the plane attributes to make the determination of whether it should boost the SDR MPO plane.

## -remarks

## -see-also
