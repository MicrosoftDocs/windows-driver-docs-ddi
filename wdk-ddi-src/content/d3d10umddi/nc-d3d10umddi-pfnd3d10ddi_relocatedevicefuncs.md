---
UID: NC:d3d10umddi.PFND3D10DDI_RELOCATEDEVICEFUNCS
title: PFND3D10DDI_RELOCATEDEVICEFUNCS
author: windows-driver-content
description: The RelocateDeviceFuncs function notifies the user-mode display driver about the new location of the driver function table.
old-location: display\relocatedevicefuncs.htm
old-project: display
ms.assetid: 3932a2a1-7b1d-4921-bd4a-905b44166091
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D10DDI_RELOCATEDEVICEFUNCS, RelocateDeviceFuncs, RelocateDeviceFuncs callback function [Display Devices], UserModeDisplayDriverDx10_Functions_01a40916-8ba8-4e29-87d7-32e9c3fe337f.xml, d3d10umddi/RelocateDeviceFuncs, display.relocatedevicefuncs
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
-	RelocateDeviceFuncs
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_RELOCATEDEVICEFUNCS callback


## -description


The <i>RelocateDeviceFuncs</i> function notifies the user-mode display driver about the new location of the driver function table. 


## -parameters




### -param Arg1


### -param *








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pDeviceFunctions [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a> structure that contains pointers to the functions of the user-mode display driver. 


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code.




## -remarks



A user-mode display driver can use the <i>RelocateDeviceFuncs</i> function to replace function pointers in the driver function table. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

