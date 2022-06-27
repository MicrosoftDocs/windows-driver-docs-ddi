---
UID: NC:d3dkmddi.DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT3
title: DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT3 (d3dkmddi.h)
description: The following new function is called to determine whether a specific multi-plane overlay configuration is supported.
old-location: display\dxgkddi_checkmultiplaneoverlaysupport3.htm
ms.date: 04/20/2022
keywords: ["DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT3 callback function"]
ms.keywords: DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT3, DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT3 callback, DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT3 callback function [Display Devices], d3dkmddi/DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT3, display.dxgkddi_checkmultiplaneoverlaysupport3
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607 (WDDM 2.1)
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
req.typenames: 
f1_keywords:
 - DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT3
 - d3dkmddi/DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT3
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT3
---

# DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT3 callback function

## -description

In WDDM 2.1 and later versions, the DirectX graphics kernel subsystem calls a driver's **DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT3** callback routine to determine whether a specific multi-plane overlay configuration is supported.  It must be implemented by WDDM 2.1 and later verion drivers that support multi-plane overlays.

## -parameters

### -param hAdapter

Identifies the adapter containing the overlay hardware. The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the **MiniportDeviceContext** output parameter of the [**DxgkDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param pCheckMultiPlaneOverlaySupport

A pointer to a [DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT3](ns-d3dkmddi-_dxgkarg_checkmultiplaneoverlaysupport3.md) structure that describes the surfaces and display options to present.

## -returns

**DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT3** returns the following values:

| Return code | Description |
| ----------- | ----------- |
| STATUS_SUCCESS | The routine has successfully completed. |

## -remarks

The kernel mode driver reports whether the specified configuration is supported.  The kernel mode driver should not raise or lower the available bandwidth in anticipation to this configuration getting set.

This function is always called at PASSIVE level.

## -see-also

[DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT3](ns-d3dkmddi-_dxgkarg_checkmultiplaneoverlaysupport3.md)
