---
UID: NC:dispmprt.DXGKDDI_MIRACAST_HANDLE_IO_CONTROL
title: DXGKDDI_MIRACAST_HANDLE_IO_CONTROL (dispmprt.h)
description: Called by the operating system to request that the display miniport driver process a synchronous I/O control request in response to a user-mode display driver call to the MiracastIoControl function.
old-location: display\dxgkddimiracastiocontrol.htm
tech.root: display
ms.assetid: 83E817C3-A30D-4597-A490-C4FB93A78FCE
ms.date: 05/10/2018
keywords: ["DXGKDDI_MIRACAST_HANDLE_IO_CONTROL callback function"]
ms.keywords: DXGKDDI_MIRACAST_HANDLE_IO_CONTROL, DXGKDDI_MIRACAST_HANDLE_IO_CONTROL callback, DxgkDdiMiracastIoControl, DxgkDdiMiracastIoControl callback function [Display Devices], display.dxgkddimiracastiocontrol, dispmprt/DxgkDdiMiracastIoControl
f1_keywords:
 - "dispmprt/DxgkDdiMiracastIoControl"
 - "DxgkDdiMiracastIoControl"
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
- DxgkDdiMiracastIoControl
targetos: Windows
req.typenames: 
---

# DXGKDDI_MIRACAST_HANDLE_IO_CONTROL callback function


## -description


Called by the operating system to request that the display miniport driver process a synchronous I/O control request in response to a user-mode display driver call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_miracast_io_control">MiracastIoControl</a> function.


## -parameters




### -param DriverContext 
[in]
A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


### -param MiracastContext 
[in]
The Miracast device context, supplied by the operating system. This context was provided by the display miniport driver in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_miracast_create_context">DxgkDdiMiracastCreateContext</a> function.


### -param InputBufferSize 
[in]
Supplied by the operating system as the size, in bytes, of the input buffer pointed to by <i>pInputBuffer</i>. This value originated as the user-mode <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_miracast_io_control">MiracastIoControl</a> function's <i>InputBufferSize</i> parameter.


### -param pInputBuffer 
[in]
Supplied by the operating system as a pointer to the input buffer. This value originated as the user-mode <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_miracast_io_control">MiracastIoControl</a> function's <i>InputBufferSize</i> parameter.

<i>InputBufferSize</i> specifies the size of the buffer.


### -param OutputBufferSize 
[in]
Supplied by the operating system as the size, in bytes, of the output buffer pointed to by <i>pOutputBuffer</i>.

This value originated as the user-mode <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_miracast_io_control">MiracastIoControl</a> function's <i>OutputBufferSize</i> parameter.

### -param pOutputBuffer 
[out]
Supplied by the operating system as a pointer to the output buffer. This value originated as the user-mode <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_miracast_io_control">MiracastIoControl</a> function's <i>pOutputBuffer</i> parameter.

<i>OutBufferSize</i> specifies the size of the buffer.


### -param BytesReturned 
[out]
Supplied by the operating system as a pointer to a buffer that holds a <b>ULONG</b>-type value that is the number of bytes that the display miniport driver returned in the buffer pointed to by <i>pOutputBuffer</i>.






## -returns



Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes that are defined in Ntstatus.h.




## -remarks



The operating system guarantees that a call to <i>DxgkDdiMiracastIoControl</i> occurs in the same process space as the user-mode <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_miracast_io_control">MiracastIoControl</a> request is called in. 

Even though the operating system merely copies the values of the input and output buffer sizes from the respective parameters of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_miracast_io_control">MiracastIoControl</a>, the display miniport driver is responsible for checking buffer sizes before using the buffers. Also, the driver should perform probing operations within a try/except calling block, using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-probeforread">ProbeForRead</a> and/or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-probeforwrite">ProbeForWrite</a> functions, to verify any user-mode memory that input buffers point to.

This I/O control operation is processed synchronously with a call to the user-mode <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_miracast_io_control">MiracastIoControl</a> function.

<h3><a id="Synchronization"></a><a id="synchronization"></a><a id="SYNCHRONIZATION"></a>Synchronization</h3>
The operating system groups the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_miracast_create_context">DxgkDdiMiracastCreateContext</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_miracast_destroy_context">DxgkDdiMiracastDestroyContext</a>, and <i>DxgkDdiMiracastIoControl</i> functions as a <i>Miracast</i> class. 

The threading and synchronization level for this function is set by how the user-mode driver sets the <i>HardwareAccess</i> parameter in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_miracast_io_control">MiracastIoControl</a> function:<ul>
<li>If <i>HardwareAccess</i> is <b>FALSE</b>, then the operating system guarantees that <i>DxgkDdiMiracastIoControl</i> follows the second-level synchronization mode as defined in <a href="https://docs.microsoft.com/windows-hardware/drivers/display/threading-and-synchronization-second-level">Threading and Synchronization Second Level</a>. <i>DxgkDdiMiracastIoControl</i> can be called when other level 0, 1, or non-Miracast classes of level 2 functions are being called on another thread context. However, only one of the level 2 Miracast-class functions can be called at a time.</li>
<li>If <i>HardwareAccess</i> is <b>TRUE</b>, then <i>DxgkDdiMiracastIoControl</i> follows the third-level synchronization mode as defined in <a href="https://docs.microsoft.com/windows-hardware/drivers/display/threading-and-synchronization-third-level">Threading and Synchronization Third Level</a>. Note that the flushing of the GPU will create substantial processing overhead.</li>
</ul>





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_miracast_create_context">DxgkDdiMiracastCreateContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_miracast_io_control">MiracastIoControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-probeforread">ProbeForRead</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-probeforwrite">ProbeForWrite</a>
 

 

