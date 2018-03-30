---
UID: NC:netdispumdddi.PFN_MIRACAST_IO_CONTROL
title: PFN_MIRACAST_IO_CONTROL
author: windows-driver-content
description: Called by the user-mode display driver to send the kernel-mode display miniport driver a synchronous I/O control request.The data type of this function is PFN_MIRACAST_IO_CONTROL.
old-location: display\miracastiocontrol.htm
old-project: display
ms.assetid: df63ec18-79e0-40a6-a412-46071eb8a7fe
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: MiracastIoControl, MiracastIoControl callback function [Display Devices], PFN_MIRACAST_IO_CONTROL, display.miracastiocontrol, netdispumdddi/MiracastIoControl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Netdispumdddi.h
api_name:
-	MiracastIoControl
product: Windows
targetos: Windows
req.typenames: NDK_SRQ_DISPATCH
---

# PFN_MIRACAST_IO_CONTROL callback


## -description


Called by the user-mode display driver to send the kernel-mode  display miniport driver a synchronous I/O control request.The data type of this function is <b>PFN_MIRACAST_IO_CONTROL</b>.




## -parameters




### -param hMiracastDeviceHandle [in]

A handle that represents a Miracast device. The Miracast user-mode driver previously obtained this handle as the <i>hMiracastDeviceHandle</i> parameter in a call to the <a href="https://msdn.microsoft.com/3b10ddd9-a48d-4f96-b35e-db017d1f9583">CreateMiracastContext</a> function.


### -param HardwareAccess [in]

A Boolean value that indicates whether this I/O control request from the user-mode display driver needs to flush all the pending GPU DMA buffers.

We don't recommend that the driver set this value to <b>TRUE</b> except when necessary, because flushing the GPU will create substantial processing overhead.


### -param InputBufferSize [in]

The size, in bytes, of the input buffer pointed to by <i>pInputBuffer</i>.


### -param *pInputBuffer [in]

A pointer to the input buffer. The <i>InputBufferSize</i> parameter specifies the size of the buffer.


### -param OutputBufferSize [in]

The size, in bytes, of the output buffer pointed to by <i>pOutputBuffer</i>.


### -param *pOutputBuffer [out]

A driver-supplied pointer to the output buffer. The <i>OutputBufferSize</i> parameter specifies the size of the buffer.


### -param *pBytesReturned [out, optional]

An optional driver-supplied pointer to a <b>UINT</b>-type variable that holds the number of bytes that the display miniport driver returned.


## -returns



On success, the operating system returns <b>STATUS_SUCCESS</b>. Otherwise, the function returns an error code defined in the Ntstatus.h header.




## -remarks



If the Miracast user-mode driver calls <b>MiracastIoControl</b> when the operating system is starting a Miracast session, and if the calling thread is not the thread in which the operating system calls the <a href="https://msdn.microsoft.com/2778d9d0-7f97-416f-a5ae-3754b17e8a29">StartMiracastSession</a> function, the operating system blocks the <b>MiracastIoControl</b> call until the Miracast start session is finished. If the user-mode driver calls <b>MiracastIoControl</b> in the same context as is used in  the <a href="https://msdn.microsoft.com/3b10ddd9-a48d-4f96-b35e-db017d1f9583">CreateMiracastContext</a> or <i>StartMiracastSession</i> functions, the operating system will process the call.

If the Miracast user-mode driver calls <b>MiracastIoControl</b> when the operating system is stopping a Miracast session, and if the calling thread is not the thread in which the operating system calls the <a href="https://msdn.microsoft.com/ab9ad8ee-9390-41a4-9a69-2e98579b2b77">StopMiracastSession</a> function, the operating system will fail this call. If the user-mode driver calls <b>MiracastIoControl</b> in the same context as is used in  the <i>StopMiracastSession</i> or <a href="https://msdn.microsoft.com/1b155e15-1e4e-45bb-98cc-f1c19923ed2c">DestroyMiracastContext</a> functions, the operating system will process the call.




## -see-also




<a href="https://msdn.microsoft.com/3b10ddd9-a48d-4f96-b35e-db017d1f9583">CreateMiracastContext</a>



<a href="https://msdn.microsoft.com/1b155e15-1e4e-45bb-98cc-f1c19923ed2c">DestroyMiracastContext</a>



<a href="https://msdn.microsoft.com/2778d9d0-7f97-416f-a5ae-3754b17e8a29">StartMiracastSession</a>



<a href="https://msdn.microsoft.com/ab9ad8ee-9390-41a4-9a69-2e98579b2b77">StopMiracastSession</a>
 

 

