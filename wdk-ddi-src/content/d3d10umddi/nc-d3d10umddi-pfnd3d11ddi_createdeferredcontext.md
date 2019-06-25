---
UID: NC:d3d10umddi.PFND3D11DDI_CREATEDEFERREDCONTEXT
title: PFND3D11DDI_CREATEDEFERREDCONTEXT (d3d10umddi.h)
description: The CreateDeferredContext function creates a deferred context.
old-location: display\createdeferredcontext.htm
ms.assetid: 464a2291-55c8-4e51-ba08-219ce426d038
ms.date: 05/10/2018
ms.keywords: CreateDeferredContext, CreateDeferredContext callback function [Display Devices], PFND3D11DDI_CREATEDEFERREDCONTEXT, PFND3D11DDI_CREATEDEFERREDCONTEXT callback, UserModeDisplayDriverDx11_Functions_8de581fa-3b85-4827-bf32-f0b96d011202.xml, d3d10umddi/CreateDeferredContext, display.createdeferredcontext
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CreateDeferredContext is supported beginning with the Windows 7 operating system.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3d10umddi.h
api_name:
- CreateDeferredContext
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11DDI_CREATEDEFERREDCONTEXT callback function


## -description


The <b>CreateDeferredContext</b> function creates a deferred context.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param *

*pCreateDeferredContext* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createdeferredcontext">D3D11DDIARG_CREATEDEFERREDCONTEXT</a> structure that describes the parameters that the user-mode display driver uses to create a deferred context. 


## -returns



None

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver is only required to implement <b>CreateDeferredContext</b> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability that can be returned in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11ddi_threading_caps">D3D11DDI_THREADING_CAPS</a> structure from a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10_2ddi_getcaps">GetCaps(D3D10_2)</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createdeferredcontext">D3D11DDIARG_CREATEDEFERREDCONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11ddi_threading_caps">D3D11DDI_THREADING_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10_2ddi_getcaps">GetCaps(D3D10_2)</a>
 

 

