---
UID: NC:dispmprt.DXGKDDI_DSICAPS
title: DXGKDDI_DSICAPS
ms.date: 11/8/2019
ms.topic: language-reference
targetos: Windows
description: The DxgkddiDsiCaps function queries the Display Serial Interface (DSI) capabilities for a particular target.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dispmprt.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: The next version of Windows 10
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_DSICAPS
f1_keywords:
 - dispmprt/DXGKDDI_DSICAPS
dev_langs:
 - c++
---

# DXGKDDI_DSICAPS callback function

## -description

The *DxgkddiDsiCaps* callback function queries the Display Serial Interface (DSI) capabilities for a particular target.

## -parameters

### -param Context

[in] As retrieved from the driver's MIPI interface (DXGK_MIPIDSI_interface ,_ DXGK queries the driver for this context.

### -param TargetId

[in] Target identifier of the monitor.

### -param pArgs

[out] Pointer to a [DXGI_DSI_CAPS](ns-dispmprt-dxgk_dsi_caps.md) structure.

## -returns

*DxgkddiDsiCaps* returns STATUS_SUCCESS if it succeeds; otherwise it returns one of the error codes defined in *Ntstatus.h*.

## -remarks

An OEM panel driver should initialize by sending [IOCTL_MIPI_DSI_QUERY_CAPS]() which provides information to allow the OEM panel driver to verify driver support, and provides the raw level 1 DDB data from the display to allow one panel driver to support multiple devices and to confirm that there is no mismatch. The OS graphics kernel calls DxgkddiDsiCaps when it receives this IOCTL. The capabilities are returned in a DXGK_DSI_CAPS structure.

The graphics driver fills in the [DXGI_DSI_CAPS](ns-dispmprt-dxgk_dsi_caps.md) fields, using cached information if available since the data should be static. Since the OS needs the`TargetMaximumReturnPacketSize` field value for packet validation, it can request the capabilities from the graphics driver before receiving a request from the panel driver.

The OEM panel driver is responsible for validating DSI capability and compatibility with the panel, since neither the graphics driver nor the OS has sufficient information to do so, particularly for any manufacturer defined or undefined elements.

## -see-also

[DXGI_DSI_CAPS](ns-dispmprt-dxgk_dsi_caps.md)

[IOCTL_MIPI_DSI_QUERY_CAPS]()
