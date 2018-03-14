---
UID: NC:dispmprt.DXGKDDI_MIRACAST_DESTROY_CONTEXT
title: DXGKDDI_MIRACAST_DESTROY_CONTEXT
author: windows-driver-content
description: Destroys an instance of a Miracast device.
old-location: display\dxgkddimiracastdestroycontext.htm
old-project: display
ms.assetid: 2DEEB379-C9E8-45E4-920D-D94F8C27A4EF
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_MIRACAST_DESTROY_CONTEXT, DxgkDdiMiracastDestroyContext, DxgkDdiMiracastDestroyContext callback function [Display Devices], display.dxgkddimiracastdestroycontext, dispmprt/DxgkDdiMiracastDestroyContext
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Dispmprt.h
api_name:
-	DxgkDdiMiracastDestroyContext
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGKDDI_MIRACAST_DESTROY_CONTEXT callback


## -description


Destroys an instance of a Miracast device.


## -prototype


````
DXGKDDI_MIRACAST_DESTROY_CONTEXT DxgkDdiMiracastDestroyContext;

VOID* DxgkDdiMiracastDestroyContext(
  _In_ PVOID DriverContext,
  _In_ PVOID MiracastContext
)
{ ... }
````


## -parameters




### -param DriverContext [in]

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


### -param MiracastContext [in]

The Miracast device context, supplied by the operating system. This context was previously provided by the driver in a call to the <a href="..\dispmprt\nc-dispmprt-dxgkddi_miracast_create_context.md">DxgkDdiMiracastCreateContext</a> function.


## -returns



This callback function does not return a value.




## -remarks



When this function is called, the display miniport driver should release all kernel-mode  resources that it allocated when it processed the <a href="..\dispmprt\nc-dispmprt-dxgkddi_miracast_create_context.md">DxgkDdiMiracastCreateContext</a> function, and it should immediately send a monitor departure hot-plug detection (HPD) awareness value to the operating system.

The operating system guarantees that, after it calls this function, it will not make any more calls to the <a href="..\dispmprt\nc-dispmprt-dxgkddi_miracast_handle_io_control.md">DxgkDdiMiracastIoControl</a> function.

If a Miracast device is disconnected before the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_commitvidpn.md">DxgkDdiCommitVidPn</a> function completes, while a present operation is still occurring on this Miracast target, the display miniport driver should not send any data to the user-mode Miracast driver.

If the user-mode <a href="..\netdispumdddi\nc-netdispumdddi-pfn_stop_miracast_session.md">StopMiracastSession</a> function takes too long to complete, the operating system calls <i>DxgkDdiMiracastDestroyContext</i> while the user-mode Miracast driver is still running. In this case, the operating system blocks any further calls to the user-mode <a href="..\netdispumdddi\nc-netdispumdddi-pfn_miracast_io_control.md">MiracastIoControl</a> function.

<h3><a id="Synchronization"></a><a id="synchronization"></a><a id="SYNCHRONIZATION"></a>Synchronization</h3>
The operating system groups the <a href="..\dispmprt\nc-dispmprt-dxgkddi_miracast_create_context.md">DxgkDdiMiracastCreateContext</a>, <i>DxgkDdiMiracastDestroyContext</i>, and <a href="..\dispmprt\nc-dispmprt-dxgkddi_miracast_handle_io_control.md">DxgkDdiMiracastIoControl</a> functions as a <i>Miracast</i> class. The operating system guarantees that these functions follow the second-level synchronization mode as defined in <a href="https://msdn.microsoft.com/2b7c1eae-6527-469e-a2fa-74d2a1246bd3">Threading and Synchronization Second Level</a>. These functions can be called when other level 0, 1, or other classes of level 2 functions are being called on another thread context. However, only one of these level 2 Miracast-class functions can be called at a time.




## -see-also

<a href="..\netdispumdddi\nc-netdispumdddi-pfn_stop_miracast_session.md">StopMiracastSession</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_miracast_handle_io_control.md">DxgkDdiMiracastIoControl</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_commitvidpn.md">DxgkDdiCommitVidPn</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_miracast_create_context.md">DxgkDdiMiracastCreateContext</a>



<a href="..\netdispumdddi\nc-netdispumdddi-pfn_miracast_io_control.md">MiracastIoControl</a>



 

 


