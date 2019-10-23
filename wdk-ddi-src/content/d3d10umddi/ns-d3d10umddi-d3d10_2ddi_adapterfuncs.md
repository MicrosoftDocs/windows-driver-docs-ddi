---
UID: NS:d3d10umddi.D3D10_2DDI_ADAPTERFUNCS
title: D3D10_2DDI_ADAPTERFUNCS (d3d10umddi.h)
description: The D3D10_2DDI_ADAPTERFUNCS structure contains functions that the user-mode display driver can implement to communicate with a graphics adapter object.
old-location: display\d3d10_2ddi_adapterfuncs.htm
ms.assetid: b8ccd6f0-d1bf-430f-bffb-dd161793096f
ms.date: 05/10/2018
ms.keywords: D3D10_2DDI_ADAPTERFUNCS, D3D10_2DDI_ADAPTERFUNCS structure [Display Devices], UMDisplayDriver_Dx11param_Structs_6d47bf5d-d3ef-4187-83a0-95d5c3c62413.xml, d3d10umddi/D3D10_2DDI_ADAPTERFUNCS, display.d3d10_2ddi_adapterfuncs
ms.topic: struct
f1_keywords:
 - "d3d10umddi/D3D10_2DDI_ADAPTERFUNCS"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D10_2DDI_ADAPTERFUNCS is supported beginning with the Windows 7 operating system.
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d10umddi.h
api_name:
- D3D10_2DDI_ADAPTERFUNCS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D10_2DDI_ADAPTERFUNCS
---

# D3D10_2DDI_ADAPTERFUNCS structure


## -description


The D3D10_2DDI_ADAPTERFUNCS structure contains functions that the user-mode display driver can implement to communicate with a graphics adapter object. 


## -struct-fields




### -field pfnCalcPrivateDeviceSize

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivatedevicesize">CalcPrivateDeviceSize</a> function that specifies the size of a memory block that the user-mode display driver requires from the Microsoft Direct3D runtime to store frequently-accessed data.


### -field pfnCreateDevice

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function that creates a representation of a display device that handles a collection of rendering state.


### -field pfnCloseAdapter

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_closeadapter">CloseAdapter(D3D10)</a> function that releases resources for a graphics adapter object.


### -field pfnGetSupportedVersions

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10_2ddi_getsupportedversions">GetSupportedVersions</a> function that retrieves the version of the operating system that the driver supports and the hardware capabilities that are available (for example, Direct3D version 10.0, Direct3D version 10.1, and so on).


### -field pfnGetCaps

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10_2ddi_getcaps">GetCaps(D3D10_2)</a> function that queries for capabilities of the graphics hardware. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivatedevicesize">CalcPrivateDeviceSize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_closeadapter">CloseAdapter(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_openadapter">D3D10DDIARG_OPENADAPTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10_2ddi_getcaps">GetCaps(D3D10_2)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10_2ddi_getsupportedversions">GetSupportedVersions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_openadapter">OpenAdapter10</a>
 

 

