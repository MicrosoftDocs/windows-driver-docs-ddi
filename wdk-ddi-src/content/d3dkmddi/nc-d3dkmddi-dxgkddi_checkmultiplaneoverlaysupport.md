---
UID: NC:d3dkmddi.DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT
title: DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT (d3dkmddi.h)
description: Called by the Microsoft DirectX graphics kernel subsystem to check the details of hardware support for multiplane overlays.
old-location: display\dxgkddicheckmultiplaneoverlaysupport.htm
ms.date: 05/10/2018
keywords: ["DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT callback function"]
ms.keywords: DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT, DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT callback, DxgkDdiCheckMultiPlaneOverlaySupport, DxgkDdiCheckMultiPlaneOverlaySupport callback function [Display Devices], d3dkmddi/DxgkDdiCheckMultiPlaneOverlaySupport, display.dxgkddicheckmultiplaneoverlaysupport
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
req.irql: PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT
 - d3dkmddi/DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT
product:
 - Windows
---

# DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT callback function

> [!NOTE] This function has been replaced with [DxgkDdiCheckMultiPlaneOverlaySupport3](nc-d3dkmddi-dxgkddi_checkmultiplaneoverlaysupport2.md).


## -description

Called by the Microsoft DirectX graphics kernel subsystem to check the details of hardware support for multiplane overlays.

## -parameters

### -param hAdapter

A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the [DxgkDdiAddDevice](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param pCheckMultiPlaneOverlaySupport

A pointer to a [DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT](../d3dkmddi/ns-d3dkmddi-_dxgkarg_checkmultiplaneoverlaysupport.md) structure that provides details on hardware support for multiplane overlays.

## -returns

Returns <b>STATUS_SUCCESS</b> if it succeeds; otherwise it returns one of the error codes defined in Ntstatus.h.

## -see-also

[DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT](../d3dkmddi/ns-d3dkmddi-_dxgkarg_checkmultiplaneoverlaysupport.md)

[DxgkDdiAddDevice](../dispmprt/nc-dispmprt-dxgkddi_add_device.md)

