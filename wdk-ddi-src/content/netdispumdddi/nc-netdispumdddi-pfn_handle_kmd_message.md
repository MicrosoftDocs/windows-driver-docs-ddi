---
UID: NC:netdispumdddi.PFN_HANDLE_KMD_MESSAGE
title: PFN_HANDLE_KMD_MESSAGE (netdispumdddi.h)
description: Called by the operating system to handle the asynchronous kernel-mode message that the Miracast user-mode driver receives when the display miniport driver calls the DxgkCbMiracastSendMessage function.
old-location: display\handlekernelmodemessage.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFN_HANDLE_KMD_MESSAGE callback function"]
ms.keywords: HandleKernelModeMessage, HandleKernelModeMessage callback function [Display Devices], PFN_HANDLE_KMD_MESSAGE, PFN_HANDLE_KMD_MESSAGE callback, display.handlekernelmodemessage, netdispumdddi/HandleKernelModeMessage
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PFN_HANDLE_KMD_MESSAGE
 - netdispumdddi/PFN_HANDLE_KMD_MESSAGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Netdispumdddi.h
api_name:
 - PFN_HANDLE_KMD_MESSAGE
---

# PFN_HANDLE_KMD_MESSAGE callback function


## -description

Called by the operating system to handle the asynchronous kernel-mode message that the Miracast user-mode driver receives when the display miniport driver calls the <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_miracast_send_message">DxgkCbMiracastSendMessage</a> function.

## -parameters

### -param pMiracastContext [in]


A pointer to a context associated with a display adapter.

The operating system obtained the context when it called the Miracast user-mode driver's <a href="/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_create_miracast_context">CreateMiracastContext</a> function.

### -param InputBufferSize [in]


The size of the input buffer <i>pInputBuffer</i>, supplied by the operating system.

### -param pInputBuffer [in]


A pointer to the input buffer, supplied by the operating system.

### -param OutputBufferSize [in]


The size of the output buffer <i>pOutputBuffer</i>, supplied by the operating system.

### -param pOutputBuffer [out]


A pointer to the output buffer, supplied by the operating system.

### -param pBytesReturned [out]


A pointer to a buffer, supplied by the operating system, that holds the number of returned bytes that the display miniport driver wrote in <i>pOutputBuffer</i>.

## -returns

On success, this function returns <b>STATUS_SUCCESS</b>. Otherwise, the function returns an error code defined in the Ntstatus.h header.

## -remarks

#### Thread Safety

When this function is called, it's possible that it has also been called in another thread. The driver is therefore responsible for synchronizing multiple calls to <i>HandleKernelModeMessage</i> if necessary.

The operating system guarantees that this function is not called when <a href="/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_create_miracast_context">CreateMiracastContext</a>, <a href="/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_destroy_miracast_context">DestroyMiracastContext</a>, <a href="/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_start_miracast_session">StartMiracastSession</a>, and <a href="/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_stop_miracast_session">StopMiracastSession</a> are called. All the messages that the display miniport driver sends during the startup of a Miracast connected session (<i>StartMiracastSession</i>) are blocked until the session startup process has completed. The operating system also blocks all messages that the display miniport driver sends during or after a call to stop the Miracast session (<i>StopMiracastSession</i>).

## -see-also

<a href="/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_create_miracast_context">CreateMiracastContext</a>



<a href="/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_destroy_miracast_context">DestroyMiracastContext</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_miracast_send_message">DxgkCbMiracastSendMessage</a>



<a href="/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_start_miracast_session">StartMiracastSession</a>



<a href="/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_stop_miracast_session">StopMiracastSession</a>

