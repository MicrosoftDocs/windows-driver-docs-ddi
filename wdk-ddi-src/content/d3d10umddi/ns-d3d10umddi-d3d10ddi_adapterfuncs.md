---
UID: NS:d3d10umddi.D3D10DDI_ADAPTERFUNCS
title: D3D10DDI_ADAPTERFUNCS (d3d10umddi.h)
description: The D3D10DDI_ADAPTERFUNCS structure contains functions that the user-mode display driver can implement to communicate with a graphics adapter object.
old-location: display\d3d10ddi_adapterfuncs.htm
ms.assetid: 11a38b89-cc74-4921-855a-3fd795522945
ms.date: 05/10/2018
ms.keywords: D3D10DDI_ADAPTERFUNCS, D3D10DDI_ADAPTERFUNCS structure [Display Devices], UMDisplayDriver_Dx10param_Structs_6d9fe453-3734-43eb-833e-6f7deeccaf2f.xml, d3d10umddi/D3D10DDI_ADAPTERFUNCS, display.d3d10ddi_adapterfuncs
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d10umddi.h
api_name:
- D3D10DDI_ADAPTERFUNCS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D10DDI_ADAPTERFUNCS
---

# D3D10DDI_ADAPTERFUNCS structure


## -description


The D3D10DDI_ADAPTERFUNCS structure contains functions that the user-mode display driver can implement to communicate with a graphics adapter object. 


## -struct-fields




### -field pfnCalcPrivateDeviceSize

A pointer to the driver's <a href="https://msdn.microsoft.com/8221a99a-1b46-48ba-8930-ac973e009eee">CalcPrivateDeviceSize</a> function that specifies the size of a memory block that the user-mode display driver requires from the Microsoft Direct3D runtime to store frequently-accessed data.


### -field pfnCreateDevice

A pointer to the driver's <a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> function that creates a representation of a display device that handles a collection of rendering state.


### -field pfnCloseAdapter

A pointer to the driver's <a href="https://msdn.microsoft.com/bc7ccd91-becc-4596-a56a-562cfe9a18b9">CloseAdapter(D3D10)</a> function that releases resources for a graphics adapter object.


## -see-also




<a href="https://msdn.microsoft.com/8221a99a-1b46-48ba-8930-ac973e009eee">CalcPrivateDeviceSize</a>



<a href="https://msdn.microsoft.com/bc7ccd91-becc-4596-a56a-562cfe9a18b9">CloseAdapter(D3D10)</a>



<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541724">D3D10DDIARG_OPENADAPTER</a>



<a href="https://msdn.microsoft.com/50c10021-2bad-4e3c-99cc-24cf31fbc95d">OpenAdapter10</a>
 

 

