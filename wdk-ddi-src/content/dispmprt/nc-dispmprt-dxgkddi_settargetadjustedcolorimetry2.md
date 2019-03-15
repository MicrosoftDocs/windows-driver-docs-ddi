---
UID: NC:dispmprt.DXGKDDI_SETTARGETADJUSTEDCOLORIMETRY2
title: DXGKDDI_SETTARGETADJUSTEDCOLORIMETRY2 (dispmprt.h)
description: Reports the colorimetry values selected by the OS for a target.
ms.assetid: 6177791c-0854-4902-bcbb-d5a58676dbb4
ms.date: 10/19/2018
ms.topic: callback
req.header: dispmprt.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- UserDefined
api_location: 
- dispmprt.h
api_name: 
- DXGKDDI_SETTARGETADJUSTEDCOLORIMETRY2
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# DXGKDDI_SETTARGETADJUSTEDCOLORIMETRY2 callback function

## -description

Reports the colorimetry values selected by the OS for a target. The OS will call this routine whenever any of the values in the [DXGK_COLORIMETRY](../d3dkmddi/ns-d3dkmddi-_dxgk_colorimetry.md) changes or the **SdrWhiteLevel** in [DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES3 structure](https://docs.microsoft.com/en-us/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_multiplane_overlay_attributes3) changes for a target.


## -prototype

```cpp
//Declaration

DXGKDDI_SETTARGETADJUSTEDCOLORIMETRY2 DxgkddiSettargetadjustedcolorimetry2; 

// Definition

NTSTATUS DxgkddiSettargetadjustedcolorimetry2 
(
	IN_CONST_HANDLE hAdapter
	IN_PDXGKARG_SETTARGETADJUSTEDCOLORIMETRY2 pArgSetTargetAdjustedColorimetry
)
{...}

```

## -parameters

### -param hAdapter

A handle to an adapter.

### -param pArgSetTargetAdjustedColorimetry

Pointer to a [DXGKARG_SETTARGETADJUSTEDCOLORIMETRY2](ns-dispmprt-_dxgkarg_settargetadjustedcolorimetry2.md) structure containing the colorimetry related fields for the monitor attached to this target after the OS has processed the display device descriptor, all overrides and any adjustments.

## -returns

The driver returns STATUS_SUCCESS if it has updates its colorimetry values based on the supplied data.

If the driver fails, the OS will revert to standard SDR values for all parameters (i.e. 709 primaries, 2.2 gamma and 8-bit per color component RGB wire format), but it will not call the driver as this should never fail.

## -remarks

This callback function replaces [DXGKDDI_SETTARGETADJUSTEDCOLORIMETRY](nc-dispmprt-dxgkddi_settargetadjustedcolorimetry.md) and is more extensible in the future, as it contains a pointer to the DXGKARG_SETTARGETADJUSTEDCOLORIMETRY2 that can change over new releases.

## -see-also
