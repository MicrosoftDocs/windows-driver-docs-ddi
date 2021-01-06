---
UID: NC:d3d10umddi.PFND3D11DDI_RECYCLECREATEDEFERREDCONTEXT
title: PFND3D11DDI_RECYCLECREATEDEFERREDCONTEXT (d3d10umddi.h)
description: The RecycleCreateDeferredContext function clears out the pipeline state for a deferred context.
old-location: display\recyclecreatedeferredcontext.htm
ms.date: 05/10/2018
keywords: ["PFND3D11DDI_RECYCLECREATEDEFERREDCONTEXT callback function"]
ms.keywords: PFND3D11DDI_RECYCLECREATEDEFERREDCONTEXT, PFND3D11DDI_RECYCLECREATEDEFERREDCONTEXT callback, RecycleCreateDeferredContext, RecycleCreateDeferredContext callback function [Display Devices], UserModeDisplayDriverDx11_Functions_aaffc9d1-e821-41f9-badc-79d53a667644.xml, d3d10umddi/RecycleCreateDeferredContext, display.recyclecreatedeferredcontext
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: RecycleCreateDeferredContext is supported beginning with the Windows 7 operating system.
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
 - PFND3D11DDI_RECYCLECREATEDEFERREDCONTEXT
 - d3d10umddi/PFND3D11DDI_RECYCLECREATEDEFERREDCONTEXT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - RecycleCreateDeferredContext
product:
 - Windows
---

# PFND3D11DDI_RECYCLECREATEDEFERREDCONTEXT callback function


## -description

The <i>RecycleCreateDeferredContext</i> function clears out the pipeline state for a deferred context.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pCreateDeferredContext* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createdeferredcontext">D3D11DDIARG_CREATEDEFERREDCONTEXT</a> structure, which describes the parameters that the user-mode display driver uses to create a deferred context.

## -returns

<i>RecycleCreateDeferredContext</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The deferred context is successfully created.|
|E_OUTOFMEMORY|RecycleCreateDeferredContext could not allocate memory that is required for it to complete.|

## -remarks

The driver is only required to implement <i>RecycleCreateDeferredContext</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 threading-capability bit. The driver can return D3D11DDICAPS_COMMANDLISTS_BUILD_2 in the <b>Caps</b> member of the <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_threading_caps">D3D11DDI_THREADING_CAPS</a> structure from a call to the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10_2ddi_getcaps">GetCaps(D3D10_2)</a> function.

For more information about <i>RecycleCreateDeferredContext</i>, see <a href="/windows-hardware/drivers/display/introduction-to-deferred-contexts">Introduction to Deferred Contexts</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createdeferredcontext">D3D11DDIARG_CREATEDEFERREDCONTEXT</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_threading_caps">D3D11DDI_THREADING_CAPS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10_2ddi_getcaps">GetCaps(D3D10_2)</a>
