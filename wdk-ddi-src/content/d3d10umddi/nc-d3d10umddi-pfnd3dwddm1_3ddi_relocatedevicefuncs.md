---
UID: NC:d3d10umddi.PFND3DWDDM1_3DDI_RELOCATEDEVICEFUNCS
title: PFND3DWDDM1_3DDI_RELOCATEDEVICEFUNCS (d3d10umddi.h)
description: Notifies the user-mode display driver about the new location of the driver function table. Implemented by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.
old-location: display\relocatedevicefuncs_d3d11_2_.htm
ms.assetid: BA2A1F90-6E30-4055-9374-943540AE2446
ms.date: 05/10/2018
ms.keywords: PFND3DWDDM1_3DDI_RELOCATEDEVICEFUNCS, PFND3DWDDM1_3DDI_RELOCATEDEVICEFUNCS callback, RelocateDeviceFuncs(D3D11_2), RelocateDeviceFuncs(D3D11_2) callback function [Display Devices], d3d10umddi/RelocateDeviceFuncs(D3D11_2), display.relocatedevicefuncs_d3d11_2_
ms.topic: callback
f1_keywords:
 - "d3d10umddi/RelocateDeviceFuncs(D3D11_2)"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3d10umddi.h
api_name:
- RelocateDeviceFuncs(D3D11_2)
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3DWDDM1_3DDI_RELOCATEDEVICEFUNCS callback function


## -description


Notifies the user-mode display driver about the new location of the driver function table.

Implemented by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param *

*DeviceFuncs* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3dwddm1_3ddi_devicefuncs">D3DWDDM1_3DDI_DEVICEFUNCS</a> structure that contains pointers to the functions of the user-mode display driver.


## -returns



The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code.




## -remarks



A user-mode display driver can use the <i>RelocateDeviceFuncs(D3D11_2)</i> function to replace function pointers in the driver function table.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3dwddm1_3ddi_devicefuncs">D3DWDDM1_3DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3dwddm1_3ddi_relocatedevicefuncs">RelocateDeviceFuncs(D3D11_2)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
 

 

