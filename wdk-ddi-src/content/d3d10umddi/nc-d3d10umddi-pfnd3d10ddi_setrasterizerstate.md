---
UID: NC:d3d10umddi.PFND3D10DDI_SETRASTERIZERSTATE
title: PFND3D10DDI_SETRASTERIZERSTATE
author: windows-driver-content
description: The SetRasterizerState function sets the rasterizer state.
old-location: display\setrasterizerstate.htm
tech.root: display
ms.assetid: 8162c9c9-4ebd-45a9-adaf-576f25c3907e
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3D10DDI_SETRASTERIZERSTATE, PFND3D10DDI_SETRASTERIZERSTATE callback, SetRasterizerState, SetRasterizerState callback function [Display Devices], UserModeDisplayDriverDx10_Functions_4f21a729-b192-441f-b80d-cae10432ab0a.xml, d3d10umddi/SetRasterizerState, display.setrasterizerstate
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
-	SetRasterizerState
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3D10DDI_SETRASTERIZERSTATE callback function


## -description


The <i>SetRasterizerState</i> function sets the rasterizer state. 


## -parameters




### -param Arg1


### -param Arg2








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - hRasterizerState [in]

 A handle to the rasterizer state object.


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function, the Microsoft Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>SetRasterizerState</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

