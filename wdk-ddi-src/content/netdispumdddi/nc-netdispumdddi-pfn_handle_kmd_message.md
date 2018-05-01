---
UID: NC:netdispumdddi.PFN_HANDLE_KMD_MESSAGE
title: PFN_HANDLE_KMD_MESSAGE
author: windows-driver-content
description: Called by the operating system to handle the asynchronous kernel-mode message that the Miracast user-mode driver receives when the display miniport driver calls the DxgkCbMiracastSendMessage function.
old-location: display\handlekernelmodemessage.htm
old-project: display
ms.assetid: 9DE4F3B0-915A-4C66-85F8-AE248B8471B5
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: HandleKernelModeMessage, HandleKernelModeMessage callback function [Display Devices], PFN_HANDLE_KMD_MESSAGE, PFN_HANDLE_KMD_MESSAGE callback, display.handlekernelmodemessage, netdispumdddi/HandleKernelModeMessage
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
-	HandleKernelModeMessage
product: Windows
targetos: Windows
req.typenames: 
---

# PFN_HANDLE_KMD_MESSAGE callback function


## -description


Called by the operating system to handle the asynchronous kernel-mode message that the Miracast user-mode driver receives when the display miniport driver calls the <a href="https://msdn.microsoft.com/E8C3B9E3-854C-488D-809B-0F0893591352">DxgkCbMiracastSendMessage</a> function.


## -parameters




### -param pMiracastContext [in]

A pointer to a context associated with a display adapter.

The operating system obtained the context when it called the Miracast user-mode driver's <a href="https://msdn.microsoft.com/3b10ddd9-a48d-4f96-b35e-db017d1f9583">CreateMiracastContext</a> function.


### -param InputBufferSize [in]

The size of the input buffer <i>pInputBuffer</i>, supplied by the operating system.


### -param *pInputBuffer [in]

A pointer to the input buffer, supplied by the operating system.


### -param OutputBufferSize [in]

The size of the output buffer <i>pOutputBuffer</i>, supplied by the operating system.


### -param *pOutputBuffer [out]

A pointer to the output buffer, supplied by the operating system.


### -param *pBytesReturned [out]

A pointer to a buffer, supplied by the operating system, that holds the number of returned bytes that the display miniport driver wrote in <i>pOutputBuffer</i>.


## -returns



On success, this function returns <b>STATUS_SUCCESS</b>. Otherwise, the function returns an error code defined in the Ntstatus.h header.




## -remarks




#### Thread Safety

When this function is called, it's possible that it has also been called in another thread. The driver is therefore responsible for synchronizing multiple calls to <i>HandleKernelModeMessage</i> if necessary.

The operating system guarantees that this function is not called when <a href="https://msdn.microsoft.com/3b10ddd9-a48d-4f96-b35e-db017d1f9583">CreateMiracastContext</a>, <a href="https://msdn.microsoft.com/1b155e15-1e4e-45bb-98cc-f1c19923ed2c">DestroyMiracastContext</a>, <a href="https://msdn.microsoft.com/2778d9d0-7f97-416f-a5ae-3754b17e8a29">StartMiracastSession</a>, and <a href="https://msdn.microsoft.com/ab9ad8ee-9390-41a4-9a69-2e98579b2b77">StopMiracastSession</a> are called. All the messages that the display miniport driver sends during the startup of a Miracast connected session (<i>StartMiracastSession</i>) are blocked until the session startup process has completed. The operating system also blocks all messages that the display miniport driver sends during or after a call to stop the Miracast session (<i>StopMiracastSession</i>).




## -see-also




<a href="https://msdn.microsoft.com/3b10ddd9-a48d-4f96-b35e-db017d1f9583">CreateMiracastContext</a>



<a href="https://msdn.microsoft.com/1b155e15-1e4e-45bb-98cc-f1c19923ed2c">DestroyMiracastContext</a>



<a href="https://msdn.microsoft.com/E8C3B9E3-854C-488D-809B-0F0893591352">DxgkCbMiracastSendMessage</a>



<a href="https://msdn.microsoft.com/2778d9d0-7f97-416f-a5ae-3754b17e8a29">StartMiracastSession</a>



<a href="https://msdn.microsoft.com/ab9ad8ee-9390-41a4-9a69-2e98579b2b77">StopMiracastSession</a>
 

 

