---
UID: NC:d3d10umddi.PFND3D11_1DDI_RELOCATEDEVICEFUNCS
title: PFND3D11_1DDI_RELOCATEDEVICEFUNCS (d3d10umddi.h)
description: Notifies the user-mode display driver about the new location of the driver function table.
old-location: display\relocatedevicefuncs_d3d11_1_.htm
ms.assetid: 5d9f964e-5d7a-4b6c-977e-c718e3424f84
ms.date: 05/10/2018
ms.keywords: PFND3D11_1DDI_RELOCATEDEVICEFUNCS, PFND3D11_1DDI_RELOCATEDEVICEFUNCS callback, RelocateDeviceFuncs(D3D11_1), RelocateDeviceFuncs(D3D11_1) callback function [Display Devices], d3d10umddi/RelocateDeviceFuncs(D3D11_1), display.pfnrelocatedevicefuncs, display.relocatedevicefuncs_d3d11_1_
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3d10umddi.h
api_name:
- RelocateDeviceFuncs(D3D11_1)
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

*hDevice* [in]

A handle to the display device (graphics context).

### -param *

[in] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_devicefuncs">D3D11_1DDI_DEVICEFUNCS</a> structure that contains pointers to the functions of the user-mode display driver.



## -returns



The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code.




## -remarks



A user-mode display driver can use the <i>RelocateDeviceFuncs(D3D11_1)</i> function to replace function pointers in the driver function table.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_devicefuncs">D3D11_1DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
 

 

