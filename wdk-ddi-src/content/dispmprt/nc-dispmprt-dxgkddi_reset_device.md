---
UID: NC:dispmprt.DXGKDDI_RESET_DEVICE
title: DXGKDDI_RESET_DEVICE
author: windows-driver-content
description: The DxgkDdiResetDevice function sets a display adapter to VGA character mode (80 x 50).
old-location: display\dxgkddiresetdevice.htm
old-project: display
ms.assetid: e757e63d-6d78-4b20-9471-290f56c1bcde
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXGKDDI_RESET_DEVICE, DXGKDDI_RESET_DEVICE callback, DmFunctions_70e9fe99-65be-47a5-bb9a-fac4e10d3ae9.xml, DxgkDdiResetDevice, DxgkDdiResetDevice callback function [Display Devices], display.dxgkddiresetdevice, dispmprt/DxgkDdiResetDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
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
req.irql: Any level (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	dispmprt.h
api_name:
-	DxgkDdiResetDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKDDI_RESET_DEVICE callback function


## -description


The <i>DxgkDdiResetDevice</i> function sets a display adapter to VGA character mode (80 x 50).


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. The display miniport driver's <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


## -returns



None




## -remarks



The HAL calls this function so it can display information on the screen during hibernation, bug checks, and the like.

<i>DxgkDdiResetDevice</i> can be called at any IRQL, so it must be in nonpageable memory. <i>DxgkDdiResetDevice</i> must not call any code that is in pageable memory and must not manipulate any data that is in pageable memory.



