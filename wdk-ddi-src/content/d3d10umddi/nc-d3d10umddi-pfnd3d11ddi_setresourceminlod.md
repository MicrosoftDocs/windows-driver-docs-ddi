---
UID: NC:d3d10umddi.PFND3D11DDI_SETRESOURCEMINLOD
title: PFND3D11DDI_SETRESOURCEMINLOD (d3d10umddi.h)
description: The SetResourceMinLOD function sets the minimum level of detail (LOD) for a resource.
old-location: display\setresourceminlod.htm
ms.assetid: a54b2fa7-c0c2-42b7-ae89-7984282d4af4
ms.date: 05/10/2018
ms.keywords: PFND3D11DDI_SETRESOURCEMINLOD, PFND3D11DDI_SETRESOURCEMINLOD callback, SetResourceMinLOD, SetResourceMinLOD callback function [Display Devices], UserModeDisplayDriverDx11_Functions_3c56a9a6-a13e-4377-a997-e84af3ff12ef.xml, d3d10umddi/SetResourceMinLOD, display.setresourceminlod
ms.topic: callback
f1_keywords:
 - "d3d10umddi/SetResourceMinLOD"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: SetResourceMinLOD is supported beginning with the Windows 7 operating system.
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
- SetResourceMinLOD
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11DDI_SETRESOURCEMINLOD callback function


## -description


The <i>SetResourceMinLOD</i> function sets the minimum level of detail (LOD) for a resource. 


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hResource* [in]

A handle to the driver's private data for the resource. 

### -param Arg3

*MinLOD* [in]

A single-precision float vector to set for the minimum level of detail (LOD) for the resource. 



## -returns



None

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of <i>SetResourceMinLOD</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

The Direct3D runtime calls the driver's <i>SetResourceMinLOD</i> function to set the minimum LOD (that is, the lowest MIP map) that a shader can sample from. This minimum LOD is ignored for some operations like for the operation that the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcecopy">ResourceCopy</a> function performs. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
 

 

