---
UID: NC:d3dkmddi.DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2
title: DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2 (d3dkmddi.h)
description: DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2 is called to change the overlay configuration being displayed.
old-location: display\dxgkddisetvidpnsourceaddresswithmultiplaneoverlay2.htm
ms.date: 05/10/2018
keywords: ["DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2 callback function"]
ms.keywords: DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2, DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2 callback, DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2, DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2 callback function [Display Devices], d3dkmddi/DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2, display.dxgkddisetvidpnsourceaddresswithmultiplaneoverlay2
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
req.irql: INTERRUPT_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2
 - d3dkmddi/DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2
product:
 - Windows
---

# DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2 callback function

> [!NOTE] This callback has been replaced by [DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3](nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay3.md)


## -description

<b>DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2</b> is called to change the overlay configuration being displayed. It must be implemented by Windows Display Driver Model (WDDM) 2.0 or later drivers that support multi-plane overlays.

## -parameters

### -param hAdapter

Identifies the adapter containing the overlay hardware.

### -param pSetVidPnSourceAddressWithMultiPlaneOverlay

[in] A pointer to a [DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2](ns-d3dkmddi-_dxgkarg_setvidpnsourceaddresswithmultiplaneoverlay2.md) structure that describes the surfaces and display options to present.

## -returns

If this routine succeeds, it returns <b>NTSTATUS_SUCCESS</b>. The driver should always return a success code.

## -see-also

[DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2](ns-d3dkmddi-_dxgkarg_setvidpnsourceaddresswithmultiplaneoverlay2.md)

