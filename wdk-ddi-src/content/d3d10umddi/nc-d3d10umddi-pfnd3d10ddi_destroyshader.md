---
UID: NC:d3d10umddi.PFND3D10DDI_DESTROYSHADER
title: PFND3D10DDI_DESTROYSHADER
author: windows-driver-content
description: The DestroyShader function destroys the specified shader object. The shader object can be destoyed only if it is not currently bound to a display device.
old-location: display\destroyshader.htm
old-project: display
ms.assetid: 51a3e5aa-0f17-49a6-824d-7cfe8e0a1ded
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DestroyShader, DestroyShader callback function [Display Devices], PFND3D10DDI_DESTROYSHADER, UserModeDisplayDriverDx10_Functions_798387e4-b7c1-4b03-bef7-1dad6931b432.xml, d3d10umddi/DestroyShader, display.destroyshader
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
-	DestroyShader
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_DESTROYSHADER callback


## -description


The <i>DestroyShader</i> function destroys the specified shader object. The shader object can be destoyed only if it is not currently bound to a display device. 


## -parameters




### -param Arg1


### -param Arg2








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - hShader [in]

 A handle to the driver's private data for the shader object to destroy. The Microsoft Direct3D runtime will free the memory region that it previously allocated for the object. Therefore, the driver can no longer access this memory region. 


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver should not encounter any error, except for <b>D3DDDIERR_DEVICEREMOVED</b>. Therefore, if the driver passes any error, except for <b>D3DDDIERR_DEVICEREMOVED</b>, in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function, the Microsoft Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return <b>D3DDDIERR_DEVICEREMOVED</b>; however, if device removal interfered with the operation of <i>DestroyShader</i> (which typically should not happen), the driver can return <b>D3DDDIERR_DEVICEREMOVED</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

