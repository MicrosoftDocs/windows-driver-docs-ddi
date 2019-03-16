---
UID: NC:d3dkmddi.DXGKDDI_CREATEOVERLAY
title: DXGKDDI_CREATEOVERLAY (d3dkmddi.h)
description: The DxgkDdiCreateOverlay function enables the overlay hardware if the hardware is capable.
old-location: display\dxgkddicreateoverlay.htm
ms.assetid: 1ccdd16d-fd76-4039-b538-86c77b4e8cbb
ms.date: 05/10/2018
ms.keywords: DXGKDDI_CREATEOVERLAY, DXGKDDI_CREATEOVERLAY callback, DmFunctions_61539b38-d12a-4642-926c-70c1cf1df34b.xml, DxgkDdiCreateOverlay, DxgkDdiCreateOverlay callback function [Display Devices], d3dkmddi/DxgkDdiCreateOverlay, display.dxgkddicreateoverlay
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
- DxgkDdiCreateOverlay
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_CREATEOVERLAY callback function


## -description


The <i>DxgkDdiCreateOverlay</i> function enables the overlay hardware if the hardware is capable.


## -parameters




### -param hAdapter [in]

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function.


### -param pCreateOverlay [in, out]

[in/out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557572">DXGKARG_CREATEOVERLAY</a> structure that describes the overlay.


## -returns



<i>DxgkDdiCreateOverlay</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|DxgkDdiCreateOverlay successfully created the overlay.|
|STATUS_INVALID_PARAMETER|Parameters that were passed to DxgkDdiCreateOverlay contained errors that prevented it from completing.|
|STATUS_NO_MEMORY|DxgkDdiCreateOverlay could not allocate memory that was required for it to complete.|
|STATUS_INSUFFICIENT_RESOURCES|DxgkDdiCreateOverlay could not complete because insufficient bandwidth was available or the requested overlay hardware could not complete the task.|
|STATUS_GRAPHICS_DRIVER_MISMATCH|The display miniport driver is not compatible with the user-mode display driver that initiated the call to DxgkDdiCreateOverlay.|


## -remarks



<i>DxgkDdiCreateOverlay</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557572">DXGKARG_CREATEOVERLAY</a>



<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>
 

 

