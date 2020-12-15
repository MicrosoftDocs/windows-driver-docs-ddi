---
UID: NC:d3dkmddi.DXGKDDI_RENDERGDI
title: DXGKDDI_RENDERGDI (d3dkmddi.h)
description: DxgkDdiRenderGdi is used when submitting Windows Graphics Device Interface (GDI) commands for contexts that support virtual addressing.
old-location: display\dxgkddirendergdi.htm
ms.date: 05/10/2018
keywords: ["DXGKDDI_RENDERGDI callback function"]
ms.keywords: DXGKDDI_RENDERGDI, DXGKDDI_RENDERGDI callback, DxgkDdiRenderGdi, DxgkDdiRenderGdi callback function [Display Devices], d3dkmddi/DxgkDdiRenderGdi, display.dxgkddirendergdi
req.header: d3dkmddi.h
req.include-header: 
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
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKDDI_RENDERGDI
 - d3dkmddi/DXGKDDI_RENDERGDI
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DxgkDdiRenderGdi
product:
 - Windows
---

# DXGKDDI_RENDERGDI callback function


## -description

<b>DxgkDdiRenderGdi</b> is used when submitting Windows Graphics Device Interface (GDI) commands for contexts that support virtual addressing.

## -parameters

### -param hContext

A handle to a context block that is associated with a display adapter.

### -param pRenderGdi

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_rendergdi">DXGKARG_RENDERGDI</a> structure that describes operation.

## -returns

|Value|Description|
|--- |--- |
|STATUS_SUCCESS|The submitted command is well-formed.|
|(other)|All other return values will lead to the OS bugcheck.|

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_rendergdi">DXGKARG_RENDERGDI</a>
