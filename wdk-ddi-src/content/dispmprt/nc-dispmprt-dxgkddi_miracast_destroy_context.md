---
UID: NC:dispmprt.DXGKDDI_MIRACAST_DESTROY_CONTEXT
title: DXGKDDI_MIRACAST_DESTROY_CONTEXT (dispmprt.h)
description: Destroys an instance of a Miracast device.
old-location: display\dxgkddimiracastdestroycontext.htm
tech.root: display
ms.assetid: 2DEEB379-C9E8-45E4-920D-D94F8C27A4EF
ms.date: 05/10/2018
ms.keywords: DXGKDDI_MIRACAST_DESTROY_CONTEXT, DXGKDDI_MIRACAST_DESTROY_CONTEXT callback, DxgkDdiMiracastDestroyContext, DxgkDdiMiracastDestroyContext callback function [Display Devices], display.dxgkddimiracastdestroycontext, dispmprt/DxgkDdiMiracastDestroyContext
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Dispmprt.h
api_name:
- DxgkDdiMiracastDestroyContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKDDI_MIRACAST_DESTROY_CONTEXT callback function


## -description


Destroys an instance of a Miracast device.


## -parameters




### -param DriverContext [in]

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


### -param MiracastContext [in]

The Miracast device context, supplied by the operating system. This context was previously provided by the driver in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_miracast_create_context">DxgkDdiMiracastCreateContext</a> function.


## -returns



This callback function does not return a value.




## -remarks



When this function is called, the display miniport driver should release all kernel-mode  resources that it allocated when it processed the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_miracast_create_context">DxgkDdiMiracastCreateContext</a> function, and it should immediately send a monitor departure hot-plug detection (HPD) awareness value to the operating system.

The operating system guarantees that, after it calls this function, it will not make any more calls to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_miracast_handle_io_control">DxgkDdiMiracastIoControl</a> function.

If a Miracast device is disconnected before the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_commitvidpn">DxgkDdiCommitVidPn</a> function completes, while a present operation is still occurring on this Miracast target, the display miniport driver should not send any data to the user-mode Miracast driver.

If the user-mode <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/netdispumdddi/nc-netdispumdddi-pfn_stop_miracast_session">StopMiracastSession</a> function takes too long to complete, the operating system calls <i>DxgkDdiMiracastDestroyContext</i> while the user-mode Miracast driver is still running. In this case, the operating system blocks any further calls to the user-mode <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/netdispumdddi/nc-netdispumdddi-pfn_miracast_io_control">MiracastIoControl</a> function.

<h3><a id="Synchronization"></a><a id="synchronization"></a><a id="SYNCHRONIZATION"></a>Synchronization</h3>
The operating system groups the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_miracast_create_context">DxgkDdiMiracastCreateContext</a>, <i>DxgkDdiMiracastDestroyContext</i>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_miracast_handle_io_control">DxgkDdiMiracastIoControl</a> functions as a <i>Miracast</i> class. The operating system guarantees that these functions follow the second-level synchronization mode as defined in <a href="https://docs.microsoft.com/windows-hardware/drivers/display/threading-and-synchronization-second-level">Threading and Synchronization Second Level</a>. These functions can be called when other level 0, 1, or other classes of level 2 functions are being called on another thread context. However, only one of these level 2 Miracast-class functions can be called at a time.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_commitvidpn">DxgkDdiCommitVidPn</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_miracast_create_context">DxgkDdiMiracastCreateContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_miracast_handle_io_control">DxgkDdiMiracastIoControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/netdispumdddi/nc-netdispumdddi-pfn_miracast_io_control">MiracastIoControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/netdispumdddi/nc-netdispumdddi-pfn_stop_miracast_session">StopMiracastSession</a>
 

 

