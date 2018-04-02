---
UID: NS:d3d10umddi.D3D10_2DDI_ADAPTERFUNCS
title: D3D10_2DDI_ADAPTERFUNCS
author: windows-driver-content
description: The D3D10_2DDI_ADAPTERFUNCS structure contains functions that the user-mode display driver can implement to communicate with a graphics adapter object.
old-location: display\d3d10_2ddi_adapterfuncs.htm
old-project: display
ms.assetid: b8ccd6f0-d1bf-430f-bffb-dd161793096f
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D10_2DDI_ADAPTERFUNCS, D3D10_2DDI_ADAPTERFUNCS structure [Display Devices], UMDisplayDriver_Dx11param_Structs_6d47bf5d-d3ef-4187-83a0-95d5c3c62413.xml, d3d10umddi/D3D10_2DDI_ADAPTERFUNCS, display.d3d10_2ddi_adapterfuncs
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3d10umddi.h
api_name:
-	D3D10_2DDI_ADAPTERFUNCS
product: Windows
targetos: Windows
req.typenames: D3D10_2DDI_ADAPTERFUNCS
---

# D3D10_2DDI_ADAPTERFUNCS structure


## -description


The D3D10_2DDI_ADAPTERFUNCS structure contains functions that the user-mode display driver can implement to communicate with a graphics adapter object. 


## -struct-fields




### -field pfnCalcPrivateDeviceSize

A pointer to the driver's <a href="https://msdn.microsoft.com/8221a99a-1b46-48ba-8930-ac973e009eee">CalcPrivateDeviceSize</a> function that specifies the size of a memory block that the user-mode display driver requires from the Microsoft Direct3D runtime to store frequently-accessed data.


### -field pfnCreateDevice

A pointer to the driver's <a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> function that creates a representation of a display device that handles a collection of rendering state.


### -field pfnCloseAdapter

A pointer to the driver's <a href="https://msdn.microsoft.com/bc7ccd91-becc-4596-a56a-562cfe9a18b9">CloseAdapter(D3D10)</a> function that releases resources for a graphics adapter object.


### -field pfnGetSupportedVersions

A pointer to the driver's <a href="https://msdn.microsoft.com/b38683f3-42f2-4f5e-9482-f72e9f2e0a34">GetSupportedVersions</a> function that retrieves the version of the operating system that the driver supports and the hardware capabilities that are available (for example, Direct3D version 10.0, Direct3D version 10.1, and so on).


### -field pfnGetCaps

A pointer to the driver's <a href="https://msdn.microsoft.com/83cd5f34-5f12-4ead-ad33-366fc3c6e804">GetCaps(D3D10_2)</a> function that queries for capabilities of the graphics hardware. 


## -see-also




<a href="https://msdn.microsoft.com/8221a99a-1b46-48ba-8930-ac973e009eee">CalcPrivateDeviceSize</a>



<a href="https://msdn.microsoft.com/bc7ccd91-becc-4596-a56a-562cfe9a18b9">CloseAdapter(D3D10)</a>



<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541724">D3D10DDIARG_OPENADAPTER</a>



<a href="https://msdn.microsoft.com/83cd5f34-5f12-4ead-ad33-366fc3c6e804">GetCaps(D3D10_2)</a>



<a href="https://msdn.microsoft.com/b38683f3-42f2-4f5e-9482-f72e9f2e0a34">GetSupportedVersions</a>



<a href="https://msdn.microsoft.com/50c10021-2bad-4e3c-99cc-24cf31fbc95d">OpenAdapter10</a>
 

 

