---
UID: NC:d3d10umddi.PFND3D11DDI_CHECKDEFERREDCONTEXTHANDLESIZES
title: PFND3D11DDI_CHECKDEFERREDCONTEXTHANDLESIZES (d3d10umddi.h)
description: The CheckDeferredContextHandleSizes function verifies the sizes of the driver-private memory spaces that hold the handle data of deferred context handles.
old-location: display\checkdeferredcontexthandlesizes.htm
ms.assetid: 0ddaec86-79e6-4d09-8403-6588b35f8b0f
ms.date: 05/10/2018
ms.keywords: CheckDeferredContextHandleSizes, CheckDeferredContextHandleSizes callback function [Display Devices], PFND3D11DDI_CHECKDEFERREDCONTEXTHANDLESIZES, PFND3D11DDI_CHECKDEFERREDCONTEXTHANDLESIZES callback, UserModeDisplayDriverDx11_Functions_f96ddf8f-1b3c-4840-b76c-2386dfb582f8.xml, d3d10umddi/CheckDeferredContextHandleSizes, display.checkdeferredcontexthandlesizes
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CheckDeferredContextHandleSizes is supported beginning with the Windows 7 operating system.
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	CheckDeferredContextHandleSizes
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11DDI_CHECKDEFERREDCONTEXTHANDLESIZES callback function


## -description


The <b>CheckDeferredContextHandleSizes</b> function verifies the sizes of the driver-private memory spaces that hold the handle data of deferred context handles.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param *pHSizes [in, out]

The size, in bytes, of the array pointed to by <i>pHandleSize</i>.


### -param *

*pHandleSize* [out, optional]

An array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff542146">D3D11DDI_HANDLESIZE</a> structures that describe the handle data of deferred context handles.


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set a critical error code. For more information about setting error codes, see the Remarks section.




## -remarks



The driver is only required to implement <i>CheckDeferredContextHandleSizes</i> if the driver supports the <b>D3D11DDICAPS_COMMANDLISTS_BUILD_2</b> capability that can be returned in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542163">D3D11DDI_THREADING_CAPS</a> structure from a call to the <a href="https://msdn.microsoft.com/83cd5f34-5f12-4ead-ad33-366fc3c6e804">GetCaps(D3D10_2)</a> function.

For more information about how <i>CheckDeferredContextHandleSizes</i> is used, see <a href="https://msdn.microsoft.com/1b3e5c29-9b9e-4c10-8fe0-706255c8fd91">Using Context-Local DDI Handles</a>. 

The driver's <i>CheckDeferredContextHandleSizes</i> function cannot call the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set the <b>D3DDDIERR_DEVICEREMOVED</b> error code because <i>CheckDeferredContextHandleSizes</i> is a capability-check type of function. The driver must ensure that it has enough information after device creation to respond to a call to <i>CheckDeferredContextHandleSizes</i>, even in the presence of <b>D3DDDIERR_DEVICEREMOVED</b>.

<i>CheckDeferredContextHandleSizes</i> should not encounter any errors. However, <i>CheckDeferredContextHandleSizes</i> might call <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> for critical errors.




## -see-also




<a href="https://msdn.microsoft.com/0ddaec86-79e6-4d09-8403-6588b35f8b0f">CheckDeferredContextHandleSizes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542141">D3D11DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542163">D3D11DDI_THREADING_CAPS</a>



<a href="https://msdn.microsoft.com/83cd5f34-5f12-4ead-ad33-366fc3c6e804">GetCaps(D3D10_2)</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

