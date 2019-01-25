---
UID: NC:d3dkmddi.DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY
title: DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY (d3dkmddi.h)
description: Sets the addresses of multiple surfaces, including the Desktop Window Manager (DWM)'s swapchain, that are associated with a particular video present source. This function is used to present multiple surfaces (including the DWM’s swapchain) to the screen.
old-location: display\dxgkddisetvidpnsourceaddresswithmultiplaneoverlay.htm
ms.assetid: 95108e45-1a3a-4a75-8719-0caadb911469
ms.date: 05/10/2018
ms.keywords: DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY, DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY callback, DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay, DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay callback function [Display Devices], d3dkmddi/DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay, display.dxgkddisetvidpnsourceaddresswithmultiplaneoverlay
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
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
req.irql: PROFILE_LEVEL  - 1
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3dkmddi.h
api_name:
-	DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY callback function


## -description


Sets the addresses of multiple surfaces, including the Desktop Window Manager (DWM)'s swapchain, that are associated with a particular video present source. This function is used to present multiple surfaces (including the DWM’s swapchain) to the screen.


## -parameters




### -param hAdapter [in]

A handle to a context block that is associated with a display adapter.

The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function.


### -param pSetVidPnSourceAddressWithMultiPlaneOverlay [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh780296">DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY</a> structure that defines multiplane overlays that are enabled for  display.


## -returns



Returns <b>STATUS_SUCCESS</b> if it succeeds; otherwise it returns one of the error codes defined in Ntstatus.h.




## -remarks



See requirements on calling this function in <a href="https://msdn.microsoft.com/BAD7FD48-905D-4547-8C69-133240B39FA3">Multiplane overlay VidPN presentation</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh780296">DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY</a>



<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>
 

 

