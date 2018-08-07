---
UID: NC:d3d10umddi.PFND3DWDDM1_3DDI_RELOCATEDEVICEFUNCS
title: PFND3DWDDM1_3DDI_RELOCATEDEVICEFUNCS
author: windows-driver-content
description: Notifies the user-mode display driver about the new location of the driver function table. Implemented by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.
old-location: display\relocatedevicefuncs_d3d11_2_.htm
tech.root: display
ms.assetid: BA2A1F90-6E30-4055-9374-943540AE2446
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3DWDDM1_3DDI_RELOCATEDEVICEFUNCS, PFND3DWDDM1_3DDI_RELOCATEDEVICEFUNCS callback, RelocateDeviceFuncs(D3D11_2), RelocateDeviceFuncs(D3D11_2) callback function [Display Devices], d3d10umddi/RelocateDeviceFuncs(D3D11_2), display.relocatedevicefuncs_d3d11_2_
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1,WDDM 1.3
req.target-min-winversvr: Windows Server 2012 R2
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
-	RelocateDeviceFuncs(D3D11_2)
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DWDDM1_3DDI_RELOCATEDEVICEFUNCS callback function


## -description


Notifies the user-mode display driver about the new location of the driver function table.

Implemented by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.


## -parameters




### -param Arg1


### -param *








#### - DeviceFuncs [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn458988">D3DWDDM1_3DDI_DEVICEFUNCS</a> structure that contains pointers to the functions of the user-mode display driver.


#### - hDevice

A handle to the display device (graphics context).


## -returns



The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code.




## -remarks



A user-mode display driver can use the <i>RelocateDeviceFuncs(D3D11_2)</i> function to replace function pointers in the driver function table.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn458988">D3DWDDM1_3DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/BA2A1F90-6E30-4055-9374-943540AE2446">RelocateDeviceFuncs(D3D11_2)</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

