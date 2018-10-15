---
UID: NC:dispmprt.DXGK_BRIGHTNESS_GET
title: DXGK_BRIGHTNESS_GET
author: windows-driver-content
description: The DxgkDdiGetBrightness function retrieves the currently active brightness level of an integrated display panel.
old-location: display\dxgkddigetbrightness.htm
tech.root: display
ms.assetid: e226cd36-45af-4d80-9aba-8919b267483b
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DXGK_BRIGHTNESS_GET, DXGK_BRIGHTNESS_GET callback, DmFunctions_be286481-7cef-4059-acb2-cac6554eb346.xml, DxgkDdiGetBrightness, DxgkDdiGetBrightness callback function [Display Devices], display.dxgkddigetbrightness, dispmprt/DxgkDdiGetBrightness
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	dispmprt.h
api_name:
-	DxgkDdiGetBrightness
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGK_BRIGHTNESS_GET callback function


## -description


The <i>DxgkDdiGetBrightness</i> function retrieves the currently active brightness level of an integrated display panel.


## -prototype


```
DXGK_BRIGHTNESS_GET DxgkDdiGetBrightness;

NTSTATUS* DxgkDdiGetBrightness(
  _In_ PVOID  Context,
  _In_ PUCHAR Brightness
)
{ ... }
```


## -parameters




### -param Context

[in] A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem.


### -param Brightness

[in] A pointer to a variable that receives the brightness level.


## -returns



<i>DxgkDdiGetBrightness</i> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes that are defined in <i>Ntstatus.h</i>.




## -remarks



When the <a href="https://msdn.microsoft.com/6352c3fd-1a5f-4137-b76e-35c5b82a56c7">monitor driver</a> initializes, it can call the display miniport driver's <i>DxgkDdiGetBrightness</i> function to retrieve the brightness level that will be currently active for the integrated display panel.

Because the monitor driver always gets the brightness level for the integrated display panel on boot or resume and all changes in brightness go through the monitor driver, the monitor driver should always have the current brightness level cached. Therefore, when clients query for the current brightness level, the level is queried from the monitor driver and not from the display miniport driver.

<i>DxgkDdiGetBrightness</i> should be made pageable.




## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>



 

 


