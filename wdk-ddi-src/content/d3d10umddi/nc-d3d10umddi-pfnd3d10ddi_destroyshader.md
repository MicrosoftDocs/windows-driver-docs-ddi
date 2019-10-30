---
UID: NC:d3d10umddi.PFND3D10DDI_DESTROYSHADER
title: PFND3D10DDI_DESTROYSHADER (d3d10umddi.h)
description: The DestroyShader function destroys the specified shader object. The shader object can be destoyed only if it is not currently bound to a display device.
old-location: display\destroyshader.htm
ms.assetid: 51a3e5aa-0f17-49a6-824d-7cfe8e0a1ded
ms.date: 05/10/2018
ms.keywords: DestroyShader, DestroyShader callback function [Display Devices], PFND3D10DDI_DESTROYSHADER, PFND3D10DDI_DESTROYSHADER callback, UserModeDisplayDriverDx10_Functions_798387e4-b7c1-4b03-bef7-1dad6931b432.xml, d3d10umddi/DestroyShader, display.destroyshader
ms.topic: callback
f1_keywords:
 - "d3d10umddi/DestroyShader"
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
- DestroyShader
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_DESTROYSHADER callback function


## -description


The <i>DestroyShader</i> function destroys the specified shader object. The shader object can be destoyed only if it is not currently bound to a display device. 


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hShader* [in]

A handle to the driver's private data for the shader object to destroy. The Microsoft Direct3D runtime will free the memory region that it previously allocated for the object. Therefore, the driver can no longer access this memory region. 


## -returns



None

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver should not encounter any error, except for <b>D3DDDIERR_DEVICEREMOVED</b>. Therefore, if the driver passes any error, except for <b>D3DDDIERR_DEVICEREMOVED</b>, in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Microsoft Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return <b>D3DDDIERR_DEVICEREMOVED</b>; however, if device removal interfered with the operation of <i>DestroyShader</i> (which typically should not happen), the driver can return <b>D3DDDIERR_DEVICEREMOVED</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
 

 

