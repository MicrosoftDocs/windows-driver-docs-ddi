---
UID: NC:d3d10umddi.PFND3D10DDI_CREATESHADERRESOURCEVIEW
title: PFND3D10DDI_CREATESHADERRESOURCEVIEW (d3d10umddi.h)
description: The CreateShaderResourceView function creates a shader resource view.
old-location: display\createshaderresourceview.htm
ms.assetid: 3b1c998d-3fde-4712-ba74-7c8033033182
ms.date: 05/10/2018
ms.keywords: CreateShaderResourceView, CreateShaderResourceView callback function [Display Devices], PFND3D10DDI_CREATESHADERRESOURCEVIEW, PFND3D10DDI_CREATESHADERRESOURCEVIEW callback, UserModeDisplayDriverDx10_Functions_183935f7-c6ab-4ea9-9e33-a4586daf3097.xml, d3d10umddi/CreateShaderResourceView, display.createshaderresourceview
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3d10umddi.h
api_name:
- CreateShaderResourceView
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_CREATESHADERRESOURCEVIEW callback function


## -description


The <b>CreateShaderResourceView</b> function creates a shader resource view.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param *

*pCreateShaderResourceView* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541708">D3D10DDIARG_CREATESHADERRESOURCEVIEW</a> structure that describes the parameters that the user-mode display driver uses to create a shader resource view. 

### -param Arg2

*hShaderResourceView* [in]

A handle to the driver's private data for the shader resource view. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="https://msdn.microsoft.com/2abf5ca9-974b-40d7-b71c-43c4fb33dd7c">CalcPrivateShaderResourceViewSize</a> function. The handle is really just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its shader resource view object. 

### -param Arg3

*hRTShaderResourceView* [in]

A handle to the shader resource view that the driver should use anytime it calls back into the Direct3D runtime. 



## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver might run out of memory. Therefore, the driver can pass E_OUTOFMEMORY or D3DDDIERR_DEVICEREMOVED in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is invalid; therefore, the runtime will not call the <a href="https://msdn.microsoft.com/dcdfe76e-a392-4a76-91fe-03648fec1278">DestroyShaderResourceView</a> function to destroy the handle that the <i>hShaderResourceView</i> parameter specifies.




## -see-also




<a href="https://msdn.microsoft.com/2abf5ca9-974b-40d7-b71c-43c4fb33dd7c">CalcPrivateShaderResourceViewSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541708">D3D10DDIARG_CREATESHADERRESOURCEVIEW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/dcdfe76e-a392-4a76-91fe-03648fec1278">DestroyShaderResourceView</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

