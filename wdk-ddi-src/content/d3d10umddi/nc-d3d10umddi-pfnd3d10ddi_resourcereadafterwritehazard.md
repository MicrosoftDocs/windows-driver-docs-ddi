---
UID: NC:d3d10umddi.PFND3D10DDI_RESOURCEREADAFTERWRITEHAZARD
title: PFND3D10DDI_RESOURCEREADAFTERWRITEHAZARD (d3d10umddi.h)
description: The ResourceReadAfterWriteHazard function informs the user-mode display driver that the specified resource was used as an output from the graphics processing unit (GPU) and that the resource will be used as an input to the GPU.
old-location: display\resourcereadafterwritehazard.htm
ms.assetid: 4d7dd4f5-9792-48cb-bf69-3903ac9dda75
ms.date: 05/10/2018
ms.keywords: PFND3D10DDI_RESOURCEREADAFTERWRITEHAZARD, PFND3D10DDI_RESOURCEREADAFTERWRITEHAZARD callback, ResourceReadAfterWriteHazard, ResourceReadAfterWriteHazard callback function [Display Devices], UserModeDisplayDriverDx10_Functions_6a240dd4-86e0-4876-b4c3-8dd2d3f086e8.xml, d3d10umddi/ResourceReadAfterWriteHazard, display.resourcereadafterwritehazard
f1_keywords:
 - "d3d10umddi/ResourceReadAfterWriteHazard"
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
- ResourceReadAfterWriteHazard
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_RESOURCEREADAFTERWRITEHAZARD callback function


## -description


The <i>ResourceReadAfterWriteHazard</i> function informs the user-mode display driver that the specified resource was used as an output from the graphics processing unit (GPU) and that the resource will be used as an input to the GPU. 


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hResource* [in]

A handle to the resource.


## -remarks

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 



The Microsoft Direct3D runtime calls <i>ResourceReadAfterWriteHazard</i> immediately before the specified resource is bound as an input to the GPU.

<i>ResourceReadAfterWriteHazard</i> is used with bind points other than <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setshaderresources">GsSetShaderResources</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setshaderresources">PsSetShaderResources</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setshaderresources">VsSetShaderResources</a> (for example, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_ia_setindexbuffer">IaSetIndexBuffer</a>). Because these types of bind points accept only buffers, the entire resource is considered affected by the hazard, and not just a particular view.

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>ResourceReadAfterWriteHazard</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
 

 

