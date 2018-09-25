---
UID: NC:d3d10umddi.PFND3D10DDI_SHADERRESOURCEVIEWREADAFTERWRITEHAZARD
title: PFND3D10DDI_SHADERRESOURCEVIEWREADAFTERWRITEHAZARD
author: windows-driver-content
description: The ShaderResourceViewReadAfterWriteHazard function informs the user-mode display driver that the specified resource was used as an output from the graphics processing unit (GPU) and that the resource will be used as an input to the GPU.
old-location: display\shaderresourceviewreadafterwritehazard.htm
ms.assetid: bb391154-a9ff-4032-b86e-81fa4ea2e37c
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3D10DDI_SHADERRESOURCEVIEWREADAFTERWRITEHAZARD, PFND3D10DDI_SHADERRESOURCEVIEWREADAFTERWRITEHAZARD callback, ShaderResourceViewReadAfterWriteHazard, ShaderResourceViewReadAfterWriteHazard callback function [Display Devices], UserModeDisplayDriverDx10_Functions_fa240239-13b6-43b1-a5c7-137d3d793e0c.xml, d3d10umddi/ShaderResourceViewReadAfterWriteHazard, display.shaderresourceviewreadafterwritehazard
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	ShaderResourceViewReadAfterWriteHazard
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_SHADERRESOURCEVIEWREADAFTERWRITEHAZARD callback function


## -description


The <i>ShaderResourceViewReadAfterWriteHazard</i> function informs the user-mode display driver that the specified resource was used as an output from the graphics processing unit (GPU) and that the resource will be used as an input to the GPU. A shader resource view is also provided to indicate which view caused the hazard. 


## -parameters




### -param Arg1


### -param Arg2


### -param Arg3








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - hResource [in]

 A handle to the resource.


#### - hShaderResourceView [in]

 A handle to the driver's private data for a shader resource view object. 


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The Microsoft Direct3D runtime calls <i>ShaderResourceViewReadAfterWriteHazard</i> immediately before the specified resource is bound as an input to the GPU. 

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>ShaderResourceViewReadAfterWriteHazard</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

