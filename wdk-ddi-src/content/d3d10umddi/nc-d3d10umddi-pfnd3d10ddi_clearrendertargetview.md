---
UID: NC:d3d10umddi.PFND3D10DDI_CLEARRENDERTARGETVIEW
title: PFND3D10DDI_CLEARRENDERTARGETVIEW
author: windows-driver-content
description: The ClearRenderTargetView function clears the specified render-target view by setting it to a constant value.
old-location: display\clearrendertargetview.htm
old-project: display
ms.assetid: 9dc95dd2-01ad-45d7-9e75-049026b25968
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: ClearRenderTargetView, ClearRenderTargetView callback function [Display Devices], PFND3D10DDI_CLEARRENDERTARGETVIEW, UserModeDisplayDriverDx10_Functions_b9129a55-a400-45b7-a3a9-da477170c99c.xml, d3d10umddi/ClearRenderTargetView, display.clearrendertargetview
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
-	ClearRenderTargetView
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_CLEARRENDERTARGETVIEW callback


## -description


The <b>ClearRenderTargetView</b> function clears the specified render-target view by setting it to a constant value. 


## -parameters




### -param Arg1


### -param Arg2


### -param Arg3








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - hRenderTargetView [in]

 A handle to the render-target view to clear. 


#### - pColorRGBA [in]

 A four-element array of single-precision float vectors that the driver uses to clear a render-target view. Array element 0 is red (R), 1 is green (G), 2 is blue (B), and 3 is alpha (A).


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <b>ClearRenderTargetView</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

