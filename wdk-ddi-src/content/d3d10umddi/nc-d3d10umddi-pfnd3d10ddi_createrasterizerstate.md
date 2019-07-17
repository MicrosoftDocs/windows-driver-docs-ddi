---
UID: NC:d3d10umddi.PFND3D10DDI_CREATERASTERIZERSTATE
title: PFND3D10DDI_CREATERASTERIZERSTATE (d3d10umddi.h)
description: The CreateRasterizerState function creates a rasterizer state.
old-location: display\createrasterizerstate.htm
ms.assetid: 4507b92e-2437-4f90-b527-e06773ca1e08
ms.date: 05/10/2018
ms.keywords: CreateRasterizerState, CreateRasterizerState callback function [Display Devices], PFND3D10DDI_CREATERASTERIZERSTATE, PFND3D10DDI_CREATERASTERIZERSTATE callback, UserModeDisplayDriverDx10_Functions_f190ceb6-e58c-4ab5-9abc-6339e6450c87.xml, d3d10umddi/CreateRasterizerState, display.createrasterizerstate
ms.topic: callback
f1_keywords:
 - "d3d10umddi/CreateRasterizerState"
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
- CreateRasterizerState
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_CREATERASTERIZERSTATE callback function


## -description


The <b>CreateRasterizerState</b> function creates a rasterizer state.


## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param *

*pRasterizerDesc* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10_ddi_rasterizer_desc">D3D10_DDI_RASTERIZER_DESC</a> structure that describes the parameters that the user-mode display driver uses to create a rasterizer state.

### -param Arg2

*hRTRasterizerState* [in]

A handle to the rasterizer state that the driver should use anytime it calls back into the Direct3D runtime.

### -param Arg3

*hRasterizerState* [in]

A handle to the driver's private data for the rasterizer state. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivaterasterizerstatesize">CalcPrivateRasterizerStateSize</a> function. The handle is really just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its rasterizer state object.




## -returns



None

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver can pass E_OUTOFMEMORY (if the driver runs out of memory) or D3DDDIERR_DEVICEREMOVED (if the device has been removed) in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is invalid; therefore, the runtime will not call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyrasterizerstate">DestroyRasterizerState</a> function to destroy the handle that the <i>hRasterizerState</i> parameter specifies.

The user-mode display driver is not required to create more than 4,096 unique instances of rasterizer-state objects on a device at a time. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivaterasterizerstatesize">CalcPrivateRasterizerStateSize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10_ddi_rasterizer_desc">D3D10_DDI_RASTERIZER_DESC</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyrasterizerstate">DestroyRasterizerState</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
 

 

