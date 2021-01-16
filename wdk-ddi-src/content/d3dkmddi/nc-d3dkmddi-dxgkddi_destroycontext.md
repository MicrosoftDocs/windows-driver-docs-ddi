---
UID: NC:d3dkmddi.DXGKDDI_DESTROYCONTEXT
title: DXGKDDI_DESTROYCONTEXT (d3dkmddi.h)
description: The DxgkDdiDestroyContext function destroys the specified graphics processing unit (GPU) context.
old-location: display\dxgkddidestroycontext.htm
ms.date: 05/10/2018
keywords: ["DXGKDDI_DESTROYCONTEXT callback function"]
ms.keywords: DXGKDDI_DESTROYCONTEXT, DXGKDDI_DESTROYCONTEXT callback, DmFunctions_b8cd0b48-a87b-4e6f-8811-49a1e0f46f2f.xml, DxgkDdiDestroyContext, DxgkDdiDestroyContext callback function [Display Devices], d3dkmddi/DxgkDdiDestroyContext, display.dxgkddidestroycontext
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKDDI_DESTROYCONTEXT
 - d3dkmddi/DXGKDDI_DESTROYCONTEXT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_DESTROYCONTEXT
product:
 - Windows
---

# DXGKDDI_DESTROYCONTEXT callback function


## -description

The <i>DxgkDdiDestroyContext</i> function destroys the specified graphics processing unit (GPU) context.

## -parameters

### -param hContext

[in] A handle to the context to destroy. The display miniport driver's <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createcontext">DxgkDdiCreateContext</a> function previously returned this handle in the <b>hContext</b> member of the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_createcontext">DXGKARG_CREATECONTEXT</a> structure that the <i>pCreateContext</i> parameter of <i>DxgkDdiCreateContext </i>points to.

## -returns

<i>DxgkDdiDestroyContext</i> returns STATUS_SUCCESS, or an appropriate error result if the context is not successfully destroyed.

## -remarks

A driver should free all resources that it allocated for the context and clean up any internal tracking data structures.

<i>DxgkDdiDestroyContext</i> should be made pageable.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_createcontext">DXGKARG_CREATECONTEXT</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createcontext">DxgkDdiCreateContext</a>

