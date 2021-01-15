---
UID: NC:d3dkmddi.DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT2
title: DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT2 (d3dkmddi.h)
description: DxgkDdiCheckMultiPlaneOverlaySupport2 is called to determine whether a specific multi-plane overlay configuration is supported.
old-location: display\dxgkddicheckmultiplaneoverlaysupport2.htm
ms.date: 05/10/2018
keywords: ["DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT2 callback function"]
ms.keywords: DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT2, DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT2 callback, DxgkDdiCheckMultiPlaneOverlaySupport2, DxgkDdiCheckMultiPlaneOverlaySupport2 callback function [Display Devices], d3dkmddi/DxgkDdiCheckMultiPlaneOverlaySupport2, display.dxgkddicheckmultiplaneoverlaysupport2
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
 - DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT2
 - d3dkmddi/DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT2
product:
 - Windows
---

# DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT2 callback function

> [!NOTE] This function has been replaced with [DxgkDdiCheckMultiPlaneOverlaySupport3](nc-d3dkmddi-dxgkddi_checkmultiplaneoverlaysupport2.md).


## -description

<b>DxgkDdiCheckMultiPlaneOverlaySupport2</b> is called to determine whether a specific multi-plane overlay configuration is supported.  It must be implemented by Windows Display Driver Model (WDDM) 2.0 or later drivers that support multi-plane overlays.

## -parameters

### -param hAdapter

Identifies the adapter containing the overlay hardware.

### -param pCheckMultiPlaneOverlaySupport

A pointer to a [DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2](ns-d3dkmddi-_dxgkarg_checkmultiplaneoverlaysupport2.md) structure that describes the surfaces and display options to present.

## -returns

If this routine succeeds, it returns <b>NTSTATUS_SUCCESS</b>. The driver should always return a success code.

## -remarks

The kernel mode driver reports whether the specified configuration is supported.  The kernel mode driver should not raise or lower the available bandwidth in anticipation to this configuration getting set.

## -see-also

[DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2](ns-d3dkmddi-_dxgkarg_checkmultiplaneoverlaysupport2.md)

