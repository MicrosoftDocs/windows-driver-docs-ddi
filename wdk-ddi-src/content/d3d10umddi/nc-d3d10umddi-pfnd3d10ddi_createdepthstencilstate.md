---
UID: NC:d3d10umddi.PFND3D10DDI_CREATEDEPTHSTENCILSTATE
title: PFND3D10DDI_CREATEDEPTHSTENCILSTATE (d3d10umddi.h)
description: The CreateDepthStencilState function creates a depth stencil state.
old-location: display\createdepthstencilstate.htm
ms.assetid: ed2da104-c4e8-43eb-80e0-10273b575020
ms.date: 05/10/2018
ms.keywords: CreateDepthStencilState, CreateDepthStencilState callback function [Display Devices], PFND3D10DDI_CREATEDEPTHSTENCILSTATE, PFND3D10DDI_CREATEDEPTHSTENCILSTATE callback, UserModeDisplayDriverDx10_Functions_1d472cf5-dd58-4989-afa5-12243f6c9301.xml, d3d10umddi/CreateDepthStencilState, display.createdepthstencilstate
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
- CreateDepthStencilState
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_CREATEDEPTHSTENCILSTATE callback function


## -description


The <b>CreateDepthStencilState</b> function creates a depth stencil state.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param *

*pDepthStencilDesc* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10_ddi_depth_stencil_desc">D3D10_DDI_DEPTH_STENCIL_DESC</a> structure that describes the parameters that the user-mode display driver uses to create a depth stencil state. 

### -param Arg2

*hDepthStencilState* [in]

A handle to the driver's private data for the depth stencil state. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivatedepthstencilstatesize">CalcPrivateDepthStencilStateSize</a> function. The handle is really just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its depth stencil state object.

### -param Arg3

*hRTDepthStencilState* [in]

A handle to the depth stencil state that the driver should use anytime it calls back into the Direct3D runtime. 



## -returns



None

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver can pass E_OUTOFMEMORY (if the driver runs out of memory) or D3DDDIERR_DEVICEREMOVED (if the device has been removed) in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is invalid; therefore, the runtime will not call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroydepthstencilstate">DestroyDepthStencilState</a> function to destroy the handle that the <i>hDepthStencilState</i> parameter specifies.

The user-mode display driver is not required to create more than 4,096 unique instances of depth-stencil-state objects on a device at a time. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivatedepthstencilstatesize">CalcPrivateDepthStencilStateSize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10_ddi_depth_stencilop_desc">D3D10_DDI_DEPTH_STENCILOP_DESC</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10_ddi_depth_stencil_desc">D3D10_DDI_DEPTH_STENCIL_DESC</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroydepthstencilstate">DestroyDepthStencilState</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
 

 

