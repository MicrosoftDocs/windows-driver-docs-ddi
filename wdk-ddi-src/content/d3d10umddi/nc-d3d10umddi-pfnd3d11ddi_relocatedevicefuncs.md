---
UID: NC:d3d10umddi.PFND3D11DDI_RELOCATEDEVICEFUNCS
title: PFND3D11DDI_RELOCATEDEVICEFUNCS
author: windows-driver-content
description: The RelocateDeviceFuncs(D3D11) function notifies the user-mode display driver about the new location of the driver function table.
old-location: display\relocatedevicefuncs_d3d11_.htm
ms.assetid: 1d56c71f-0108-4088-a5e0-3b41b781f361
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3D11DDI_RELOCATEDEVICEFUNCS, PFND3D11DDI_RELOCATEDEVICEFUNCS callback, RelocateDeviceFuncs, RelocateDeviceFuncs callback function [Display Devices], UserModeDisplayDriverDx11_Functions_ef0af03c-0ab5-4ea2-a568-410d1f68c183.xml, d3d10umddi/RelocateDeviceFuncs, display.relocatedevicefuncs_d3d11_
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: RelocateDeviceFuncs(D3D11) is supported beginning with the Windows 7 operating system.
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
-	RelocateDeviceFuncs
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11DDI_RELOCATEDEVICEFUNCS callback function


## -description


The <i>RelocateDeviceFuncs(D3D11)</i> function notifies the user-mode display driver about the new location of the driver function table. 


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param *



*pDeviceFunctions* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542141">D3D11DDI_DEVICEFUNCS</a> structure that contains pointers to the functions of the user-mode display driver. 


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. 




## -remarks



A user-mode display driver can use the <i>RelocateDeviceFuncs(D3D11)</i> function to replace function pointers in the driver function table. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542141">D3D11DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

