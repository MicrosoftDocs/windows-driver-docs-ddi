---
UID: NC:d3d10umddi.PFND3D10DDI_DESTROYDEPTHSTENCILSTATE
title: PFND3D10DDI_DESTROYDEPTHSTENCILSTATE (d3d10umddi.h)
description: The DestroyDepthStencilState function destroys the specified depth stencil state object. The depth stencil state object can be destoyed only if it is not currently bound to a display device.
old-location: display\destroydepthstencilstate.htm
ms.assetid: 5fc537f6-2507-4edd-bfa0-c011dd834a22
ms.date: 05/10/2018
ms.keywords: DestroyDepthStencilState, DestroyDepthStencilState callback function [Display Devices], PFND3D10DDI_DESTROYDEPTHSTENCILSTATE, PFND3D10DDI_DESTROYDEPTHSTENCILSTATE callback, UserModeDisplayDriverDx10_Functions_0d9deca1-62e7-4caa-9bfd-9c42bdd85c2c.xml, d3d10umddi/DestroyDepthStencilState, display.destroydepthstencilstate
ms.topic: callback
f1_keywords:
 - "d3d10umddi/DestroyDepthStencilState"
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
- DestroyDepthStencilState
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_DESTROYDEPTHSTENCILSTATE callback function


## -description


The <b>DestroyDepthStencilState</b> function destroys the specified depth stencil state object. The depth stencil state object can be destoyed only if it is not currently bound to a display device. 


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hDepthStencilState* [in]

A handle to the driver's private data for the depth stencil state object to destroy. The Microsoft Direct3D runtime will free the memory region that it previously allocated for the object. Therefore, the driver can no longer access this memory region. 


## -remarks

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <b>DestroyDepthStencilState</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
 

 

