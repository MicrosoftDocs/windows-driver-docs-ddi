---
UID: NC:d3d10umddi.PFND3D10DDI_DESTROYRENDERTARGETVIEW
title: PFND3D10DDI_DESTROYRENDERTARGETVIEW (d3d10umddi.h)
description: The DestroyRenderTargetView function destroys the specified render target view object. The render target view object can be destoyed only if it is not currently bound to a display device.
old-location: display\destroyrendertargetview.htm
ms.assetid: ec04fed3-8e43-4f76-af82-b36c7029f0cc
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_DESTROYRENDERTARGETVIEW callback function"]
ms.keywords: DestroyRenderTargetView, DestroyRenderTargetView callback function [Display Devices], PFND3D10DDI_DESTROYRENDERTARGETVIEW, PFND3D10DDI_DESTROYRENDERTARGETVIEW callback, UserModeDisplayDriverDx10_Functions_a2c751c2-e384-4c1a-a634-97d7f3a581be.xml, d3d10umddi/DestroyRenderTargetView, display.destroyrendertargetview
f1_keywords:
 - "d3d10umddi/DestroyRenderTargetView"
 - "DestroyRenderTargetView"
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
- DestroyRenderTargetView
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_DESTROYRENDERTARGETVIEW callback function


## -description


The <b>DestroyRenderTargetView</b> function destroys the specified render target view object. The render target view object can be destoyed only if it is not currently bound to a display device. 


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hRenderTargetView* [in]

A handle to the driver's private data for the render target view object to destroy. The Microsoft Direct3D runtime will free the memory region that it previously allocated for the object. Therefore, the driver can no longer access this memory region. 


## -remarks

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <b>DestroyRenderTargetView</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
 

 

