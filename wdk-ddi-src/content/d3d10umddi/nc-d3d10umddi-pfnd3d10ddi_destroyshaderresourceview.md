---
UID: NC:d3d10umddi.PFND3D10DDI_DESTROYSHADERRESOURCEVIEW
title: PFND3D10DDI_DESTROYSHADERRESOURCEVIEW
description: The DestroyShaderResourceView function destroys the specified shader resource view object. The shader resource view object can be destoyed only if it is not currently bound to a display device.
old-location: display\destroyshaderresourceview.htm
ms.assetid: dcdfe76e-a392-4a76-91fe-03648fec1278
ms.date: 05/10/2018
ms.keywords: DestroyShaderResourceView, DestroyShaderResourceView callback function [Display Devices], PFND3D10DDI_DESTROYSHADERRESOURCEVIEW, PFND3D10DDI_DESTROYSHADERRESOURCEVIEW callback, UserModeDisplayDriverDx10_Functions_3ca479b5-d0f1-484f-9411-1b03c3308e11.xml, d3d10umddi/DestroyShaderResourceView, display.destroyshaderresourceview
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
-	DestroyShaderResourceView
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_DESTROYSHADERRESOURCEVIEW callback function


## -description


The <b>DestroyShaderResourceView</b> function destroys the specified shader resource view object. The shader resource view object can be destoyed only if it is not currently bound to a display device. 


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hShaderResourceView* [in]

A handle to the driver's private data for the shader resource view object to destroy. The Microsoft Direct3D runtime will free the memory region that it previously allocated for the object. Therefore, the driver can no longer access this memory region. 


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <b>DestroyShaderResourceView</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

