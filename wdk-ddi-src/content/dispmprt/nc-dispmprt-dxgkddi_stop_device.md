---
UID: NC:dispmprt.DXGKDDI_STOP_DEVICE
title: DXGKDDI_STOP_DEVICE
author: windows-driver-content
description: The DxgkDdiStopDevice function resets a display adapter and frees resources allocated during DxgkDdiStartDevice.
old-location: display\dxgkddistopdevice.htm
old-project: display
ms.assetid: 3c17c7cf-9cfa-421d-a503-88726519fb6c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKDDI_STOP_DEVICE, DmFunctions_c2d7e95b-beba-488a-b046-98e5daa728b9.xml, DxgkDdiStopDevice, DxgkDdiStopDevice callback function [Display Devices], display.dxgkddistopdevice, dispmprt/DxgkDdiStopDevice
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	dispmprt.h
api_name:
-	DxgkDdiStopDevice
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGKDDI_STOP_DEVICE callback


## -description


The <i>DxgkDdiStopDevice</i> function resets a display adapter and frees resources allocated during <a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a>.


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. The display miniport driver's <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


## -returns



<i>DxgkDdiStopDevice</i> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.




## -remarks



For more information on how this function is used in Plug and Play (PnP) scenarios starting in Windows 8, see <a href="https://msdn.microsoft.com/A95DCFEA-BC1B-4A13-9850-13814725D53E">Plug and Play (PnP) in WDDM 1.2 and later</a>.

The <i>DxgkDdiStopDevice</i> function should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a>
 

 

