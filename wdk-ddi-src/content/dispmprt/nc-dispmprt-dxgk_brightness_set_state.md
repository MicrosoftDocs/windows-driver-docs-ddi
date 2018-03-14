---
UID: NC:dispmprt.DXGK_BRIGHTNESS_SET_STATE
title: DXGK_BRIGHTNESS_SET_STATE
author: windows-driver-content
description: Enables smooth brightness control on an integrated display panel.
old-location: display\dxgkddisetbrightnessstate.htm
old-project: display
ms.assetid: 804046ff-0cc7-4ff0-be07-b574cb40fd2b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGK_BRIGHTNESS_SET_STATE, DxgkDdiSetBrightnessState, DxgkDdiSetBrightnessState callback function [Display Devices], display.dxgkddisetbrightnessstate, dispmprt/DxgkDdiSetBrightnessState
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Dispmprt.h
api_name:
-	DxgkDdiSetBrightnessState
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGK_BRIGHTNESS_SET_STATE callback


## -description


Enables smooth brightness control on an integrated display panel.


## -prototype


````
DXGK_BRIGHTNESS_SET_STATE DxgkDdiSetBrightnessState;

NTSTATUS* DxgkDdiSetBrightnessState(
  _In_ PVOID                 Context,
  _In_ DXGK_BRIGHTNESS_STATE *BrightnessState
)
{ ... }
````


## -parameters




### -param Context [in]

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


### -param *BrightnessState [in]

A pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_brightness_state.md">DXGK_BRIGHTNESS_STATE</a> structure that indicates that the display miniport driver should enable the smooth brightness control for the integrated display panel.


## -returns



Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes that are defined in Ntstatus.h.




## -remarks



For the operating system to be able to adjust screen brightness smoothly, starting with Windows 8 the display miniport driver must report 10 brightness levels, expressed from 0 to 100 percent. At a level of zero percent, the screen contents should be barely visible to the user. A level of 100 percent is the maximum brightness that the integrated display panel can produce. The driver and hardware can support finer brightness control for internal operations.

When the <a href="..\dispmprt\nc-dispmprt-dxgk_brightness_set.md">DxgkDdiSetBrightness</a> function is called, the driver should select an appropriate slope to provide a smooth brightness transition based on panel characteristics, but any transition must complete in under 500 milliseconds.

This function should be made pageable.




## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgk_brightness_set.md">DxgkDdiSetBrightness</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>



 

 


