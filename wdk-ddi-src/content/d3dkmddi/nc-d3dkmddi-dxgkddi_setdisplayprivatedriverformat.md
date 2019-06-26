---
UID: NC:d3dkmddi.DXGKDDI_SETDISPLAYPRIVATEDRIVERFORMAT
title: DXGKDDI_SETDISPLAYPRIVATEDRIVERFORMAT (d3dkmddi.h)
description: The DxgkDdiSetDisplayPrivateDriverFormat function changes the private-format attribute of a video present source.
old-location: display\dxgkddisetdisplayprivatedriverformat.htm
ms.assetid: 053fdf22-20c3-4b57-94f4-0613857abfa7
ms.date: 05/10/2018
ms.keywords: DXGKDDI_SETDISPLAYPRIVATEDRIVERFORMAT, DXGKDDI_SETDISPLAYPRIVATEDRIVERFORMAT callback, DmFunctions_4171835f-0a79-4161-9bcd-c7311c9905ac.xml, DxgkDdiSetDisplayPrivateDriverFormat, DxgkDdiSetDisplayPrivateDriverFormat callback function [Display Devices], d3dkmddi/DxgkDdiSetDisplayPrivateDriverFormat, display.dxgkddisetdisplayprivatedriverformat
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3dkmddi.h
api_name:
- DxgkDdiSetDisplayPrivateDriverFormat
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_SETDISPLAYPRIVATEDRIVERFORMAT callback function


## -description


The <i>DxgkDdiSetDisplayPrivateDriverFormat</i> function changes the private-format attribute of a video present source.


## -parameters




### -param hAdapter [in]

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function.


### -param pSetDisplayPrivateDriverFormat [in]

[in] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_setdisplayprivatedriverformat">DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT</a> structure that contains function arguments.


## -returns



<i>DxgkDdiSetDisplayPrivateDriverFormat</i> returns STATUS_SUCCESS if it succeeds; otherwise, it returns STATUS_UNSUCCESSFUL to indicate that the driver could not change the private-format attribute of the given video present source.




## -remarks



The DirectX graphics kernel subsystem calls the display miniport driver's <i>DxgkDdiSetDisplayPrivateDriverFormat</i> function after the user-mode display driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_setdisplayprivatedriverformatcb">pfnSetDisplayPrivateDriverFormatCb</a> callback function. For example, the user-mode display driver might call <b>pfnSetDisplayPrivateDriverFormatCb</b> to change the swizzling format of the video present source when a full-screen flipping change is created. The DirectX graphics kernel subsystem then calls the display miniport driver's <i>DxgkDdiSetDisplayPrivateDriverFormat</i> to change the private-driver format of the video present source. This allows for the primary allocation to be displayed on the video present source without a need for translation of the primary surface.

<div class="alert"><b>Note</b>  <i>DxgkDdiSetDisplayPrivateDriverFormat</i> does not apply the private-driver format that the <b>PrivateDriverFormatAttribute</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_setdisplayprivatedriverformat">DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT</a> structure that is pointed to by <i>pSetDisplayPrivateDriverFormat</i> specifies to any allocation. <i>DxgkDdiSetDisplayPrivateDriverFormat</i> applies the private-driver format directly to the video present source. For example, <i>DxgkDdiSetDisplayPrivateDriverFormat</i> might reprogram the DAC registers to scan from a different swizzling format. </div>
<div> </div>
<i>DxgkDdiSetDisplayPrivateDriverFormat</i> should be made pageable.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_setdisplayprivatedriverformat">DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_setdisplayprivatedriverformatcb">pfnSetDisplayPrivateDriverFormatCb</a>
 

 

