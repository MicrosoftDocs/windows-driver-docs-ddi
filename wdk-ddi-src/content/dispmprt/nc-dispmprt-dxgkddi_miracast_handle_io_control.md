---
UID: NC:dispmprt.DXGKDDI_MIRACAST_HANDLE_IO_CONTROL
title: DXGKDDI_MIRACAST_HANDLE_IO_CONTROL
author: windows-driver-content
description: Called by the operating system to request that the display miniport driver process a synchronous I/O control request in response to a user-mode display driver call to the MiracastIoControl function.
old-location: display\dxgkddimiracastiocontrol.htm
old-project: display
ms.assetid: 83E817C3-A30D-4597-A490-C4FB93A78FCE
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkddimiracastiocontrol, DxgkDdiMiracastIoControl callback function [Display Devices], DxgkDdiMiracastIoControl, DXGKDDI_MIRACAST_HANDLE_IO_CONTROL, DXGKDDI_MIRACAST_HANDLE_IO_CONTROL, dispmprt/DxgkDdiMiracastIoControl
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Dispmprt.h
apiname:
-	DxgkDdiMiracastIoControl
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGKDDI_MIRACAST_HANDLE_IO_CONTROL callback


## -description


Called by the operating system to request that the display miniport driver process a synchronous I/O control request in response to a user-mode display driver call to the <a href="..\netdispumdddi\nc-netdispumdddi-pfn_miracast_io_control.md">MiracastIoControl</a> function.


## -prototype


````
DXGKDDI_MIRACAST_HANDLE_IO_CONTROL DxgkDdiMiracastIoControl;

NTSTATUS* DxgkDdiMiracastIoControl(
  _In_  PVOID DriverContext,
  _In_  PVOID MiracastContext,
  _In_  ULONG InputBufferSize,
  _In_  VOID  *pInputBuffer,
  _In_  ULONG OutBufferSize,
  _Out_ VOID  *pOutputBuffer,
  _Out_ ULONG *BytesReturned
)
{ ... }
````


## -parameters




### -param DriverContext [in]

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


### -param MiracastContext [in]

The Miracast device context, supplied by the operating system. This context was provided by the display miniport driver in a call to the <a href="..\dispmprt\nc-dispmprt-dxgkddi_miracast_create_context.md">DxgkDdiMiracastCreateContext</a> function.


### -param InputBufferSize [in]

Supplied by the operating system as the size, in bytes, of the input buffer pointed to by <i>pInputBuffer</i>. This value originated as the user-mode <a href="..\netdispumdddi\nc-netdispumdddi-pfn_miracast_io_control.md">MiracastIoControl</a> function's <i>InputBufferSize</i> parameter.


### -param *pInputBuffer [in]

Supplied by the operating system as a pointer to the input buffer. This value originated as the user-mode <a href="..\netdispumdddi\nc-netdispumdddi-pfn_miracast_io_control.md">MiracastIoControl</a> function's <i>InputBufferSize</i> parameter.

<i>InputBufferSize</i> specifies the size of the buffer.


### -param OutputBufferSize


### -param *pOutputBuffer [out]

Supplied by the operating system as a pointer to the output buffer. This value originated as the user-mode <a href="..\netdispumdddi\nc-netdispumdddi-pfn_miracast_io_control.md">MiracastIoControl</a> function's <i>pOutputBuffer</i> parameter.

<i>OutBufferSize</i> specifies the size of the buffer.


### -param *BytesReturned [out]

Supplied by the operating system as a pointer to a buffer that holds a <b>ULONG</b>-type value that is the number of bytes that the display miniport driver returned in the buffer pointed to by <i>pOutputBuffer</i>.


#### - OutBufferSize [in]

Supplied by the operating system as the size, in bytes, of the output buffer pointed to by <i>pOutputBuffer</i>.

This value originated as the user-mode <a href="..\netdispumdddi\nc-netdispumdddi-pfn_miracast_io_control.md">MiracastIoControl</a> function's <i>OutputBufferSize</i> parameter.


## -returns



Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes that are defined in Ntstatus.h.




## -remarks



The operating system guarantees that a call to <i>DxgkDdiMiracastIoControl</i> occurs in the same process space as the user-mode <a href="..\netdispumdddi\nc-netdispumdddi-pfn_miracast_io_control.md">MiracastIoControl</a> request is called in. 

Even though the operating system merely copies the values of the input and output buffer sizes from the respective parameters of <a href="..\netdispumdddi\nc-netdispumdddi-pfn_miracast_io_control.md">MiracastIoControl</a>, the display miniport driver is responsible for checking buffer sizes before using the buffers. Also, the driver should perform probing operations within a try/except calling block, using <a href="..\wdm\nf-wdm-probeforread.md">ProbeForRead</a> and/or <a href="..\wdm\nf-wdm-probeforwrite.md">ProbeForWrite</a> functions, to verify any user-mode memory that input buffers point to.

This I/O control operation is processed synchronously with a call to the user-mode <a href="..\netdispumdddi\nc-netdispumdddi-pfn_miracast_io_control.md">MiracastIoControl</a> function.

<h3><a id="Synchronization"></a><a id="synchronization"></a><a id="SYNCHRONIZATION"></a>Synchronization</h3>
The operating system groups the <a href="..\dispmprt\nc-dispmprt-dxgkddi_miracast_create_context.md">DxgkDdiMiracastCreateContext</a>, <a href="..\dispmprt\nc-dispmprt-dxgkddi_miracast_destroy_context.md">DxgkDdiMiracastDestroyContext</a>, and <i>DxgkDdiMiracastIoControl</i> functions as a <i>Miracast</i> class. 

The threading and synchronization level for this function is set by how the user-mode driver sets the <i>HardwareAccess</i> parameter in a call to the <a href="..\netdispumdddi\nc-netdispumdddi-pfn_miracast_io_control.md">MiracastIoControl</a> function:<ul>
<li>If <i>HardwareAccess</i> is <b>FALSE</b>, then the operating system guarantees that <i>DxgkDdiMiracastIoControl</i> follows the second-level synchronization mode as defined in <a href="https://msdn.microsoft.com/2b7c1eae-6527-469e-a2fa-74d2a1246bd3">Threading and Synchronization Second Level</a>. <i>DxgkDdiMiracastIoControl</i> can be called when other level 0, 1, or non-Miracast classes of level 2 functions are being called on another thread context. However, only one of the level 2 Miracast-class functions can be called at a time.</li>
<li>If <i>HardwareAccess</i> is <b>TRUE</b>, then <i>DxgkDdiMiracastIoControl</i> follows the third-level synchronization mode as defined in <a href="https://msdn.microsoft.com/780d37d9-40c6-4737-9042-473810868227">Threading and Synchronization Third Level</a>. Note that the flushing of the GPU will create substantial processing overhead.</li>
</ul>





## -see-also

<a href="..\wdm\nf-wdm-probeforread.md">ProbeForRead</a>



<a href="..\wdm\nf-wdm-probeforwrite.md">ProbeForWrite</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_miracast_create_context.md">DxgkDdiMiracastCreateContext</a>



<a href="..\netdispumdddi\nc-netdispumdddi-pfn_miracast_io_control.md">MiracastIoControl</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_MIRACAST_HANDLE_IO_CONTROL callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

