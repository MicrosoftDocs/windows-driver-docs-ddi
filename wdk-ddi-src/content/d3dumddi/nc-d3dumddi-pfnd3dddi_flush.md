---
UID: NC:d3dumddi.PFND3DDDI_FLUSH
title: PFND3DDDI_FLUSH (d3dumddi.h)
description: The Flush function submits outstanding hardware commands that are in the hardware command buffer to the display miniport driver.
old-location: display\flush.htm
tech.root: display
ms.assetid: 0c1a9a60-de17-41d1-b31d-c1d3c95d8121
ms.date: 05/10/2018
ms.keywords: Flush, Flush callback function [Display Devices], PFND3DDDI_FLUSH, PFND3DDDI_FLUSH callback, UserModeDisplayDriver_Functions_a39b804f-2f41-473f-8160-4c23655c24ec.xml, d3dumddi/Flush, display.flush
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3dumddi.h
api_name:
- Flush
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_FLUSH callback function


## -description


The <i>Flush</i> function submits outstanding hardware commands that are in the hardware command buffer to the display miniport driver.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


## -returns



<i>Flush</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|Hardware commands were successfully flushed.|
|E_OUTOFMEMORY|Flush could not allocate the required memory for it to complete.|

## -remarks



The Microsoft Direct3D runtime can call the user-mode display driver's <i>Flush</i> function at any time to notify the user-mode display driver to submit any outstanding hardware commands that are in the hardware command buffer to the display miniport driver. However, a call to <i>Flush</i> should never cause the user-mode display driver to submit invalid commands to the display miniport driver. 

To submit commands to the display miniport driver, the user-mode display driver's <i>Flush</i> function should typically call the runtime's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_rendercb">pfnRenderCb</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_rendercb">pfnRenderCb</a>
 

 

