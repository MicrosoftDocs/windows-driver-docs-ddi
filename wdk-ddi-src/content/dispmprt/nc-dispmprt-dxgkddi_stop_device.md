---
UID: NC:dispmprt.DXGKDDI_STOP_DEVICE
title: DXGKDDI_STOP_DEVICE (dispmprt.h)
description: The DxgkDdiStopDevice function resets a display adapter and frees resources allocated during DxgkDdiStartDevice.
old-location: display\dxgkddistopdevice.htm
tech.root: display
ms.assetid: 3c17c7cf-9cfa-421d-a503-88726519fb6c
ms.date: 05/10/2018
ms.keywords: DXGKDDI_STOP_DEVICE, DXGKDDI_STOP_DEVICE callback, DmFunctions_c2d7e95b-beba-488a-b046-98e5daa728b9.xml, DxgkDdiStopDevice, DxgkDdiStopDevice callback function [Display Devices], display.dxgkddistopdevice, dispmprt/DxgkDdiStopDevice
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- dispmprt.h
api_name:
- DxgkDdiStopDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKDDI_STOP_DEVICE callback function


## -description


The <i>DxgkDdiStopDevice</i> function resets a display adapter and frees resources allocated during <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a>.


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. The display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


## -returns



<i>DxgkDdiStopDevice</i> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.




## -remarks



For more information on how this function is used in Plug and Play (PnP) scenarios starting in Windows 8, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/plug-and-play--pnp--start-and-stop-cases">Plug and Play (PnP) in WDDM 1.2 and later</a>.

The <i>DxgkDdiStopDevice</i> function should be made pageable.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a>
 

 

