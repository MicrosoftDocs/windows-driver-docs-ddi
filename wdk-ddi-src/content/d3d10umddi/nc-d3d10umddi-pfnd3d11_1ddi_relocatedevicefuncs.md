---
UID: NC:d3d10umddi.PFND3D11_1DDI_RELOCATEDEVICEFUNCS
title: PFND3D11_1DDI_RELOCATEDEVICEFUNCS
author: windows-driver-content
description: Notifies the user-mode display driver about the new location of the driver function table.
old-location: display\relocatedevicefuncs_d3d11_1_.htm
ms.assetid: 5d9f964e-5d7a-4b6c-977e-c718e3424f84
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3D11_1DDI_RELOCATEDEVICEFUNCS, PFND3D11_1DDI_RELOCATEDEVICEFUNCS callback, RelocateDeviceFuncs(D3D11_1), RelocateDeviceFuncs(D3D11_1) callback function [Display Devices], d3d10umddi/RelocateDeviceFuncs(D3D11_1), display.pfnrelocatedevicefuncs, display.relocatedevicefuncs_d3d11_1_
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3d10umddi.h
api_name:
-	RelocateDeviceFuncs(D3D11_1)
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_RELOCATEDEVICEFUNCS callback function


## -description


Notifies the user-mode display driver about the new location of the driver function table.


## -parameters




### -param Arg1


### -param *








#### - [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406443">D3D11_1DDI_DEVICEFUNCS</a> structure that contains pointers to the functions of the user-mode display driver.


#### - hDevice

A handle to the display device (graphics context).


## -returns



The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code.




## -remarks



A user-mode display driver can use the <i>RelocateDeviceFuncs(D3D11_1)</i> function to replace function pointers in the driver function table.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406443">D3D11_1DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

