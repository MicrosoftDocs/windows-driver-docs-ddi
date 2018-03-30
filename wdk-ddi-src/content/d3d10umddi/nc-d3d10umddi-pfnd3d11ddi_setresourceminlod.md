---
UID: NC:d3d10umddi.PFND3D11DDI_SETRESOURCEMINLOD
title: PFND3D11DDI_SETRESOURCEMINLOD
author: windows-driver-content
description: The SetResourceMinLOD function sets the minimum level of detail (LOD) for a resource.
old-location: display\setresourceminlod.htm
old-project: display
ms.assetid: a54b2fa7-c0c2-42b7-ae89-7984282d4af4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D11DDI_SETRESOURCEMINLOD, SetResourceMinLOD, SetResourceMinLOD callback function [Display Devices], UserModeDisplayDriverDx11_Functions_3c56a9a6-a13e-4377-a997-e84af3ff12ef.xml, d3d10umddi/SetResourceMinLOD, display.setresourceminlod
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	SetResourceMinLOD
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11DDI_SETRESOURCEMINLOD callback


## -description


The <i>SetResourceMinLOD</i> function sets the minimum level of detail (LOD) for a resource. 


## -parameters




### -param Arg1


### -param Arg2


### -param Arg3








#### - MinLOD [in]

 A single-precision float vector to set for the minimum level of detail (LOD) for the resource. 


#### - hDevice [in]

 A handle to the display device (graphics context).


#### - hResource [in]

 A handle to the driver's private data for the resource. 


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function, the Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of <i>SetResourceMinLOD</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

The Direct3D runtime calls the driver's <i>SetResourceMinLOD</i> function to set the minimum LOD (that is, the lowest MIP map) that a shader can sample from. This minimum LOD is ignored for some operations like for the operation that the driver's <a href="https://msdn.microsoft.com/9a837f42-0bea-4425-b693-dd7947ac24b1">ResourceCopy</a> function performs. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542141">D3D11DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

