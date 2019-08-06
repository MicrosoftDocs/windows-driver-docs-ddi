---
UID: NC:wsk.PFN_WSK_LISTEN
title: PFN_WSK_LISTEN (wsk.h)
description: The WskListen function enables a stream socket to listen for incoming connections at the socket's bound address.
old-location: netvista\wsklisten.htm
tech.root: netvista
ms.assetid: 854C2DA1-1763-4354-8B9D-9AE0C60D8F31
ms.date: 05/02/2018
ms.keywords: PFN_WSK_LISTEN, PFN_WSK_LISTEN callback, WskListen, WskListen callback function [Network Drivers Starting with Windows Vista], netvista.wsklisten, wsk/WskListen
ms.topic: callback
f1_keywords:
 - "wsk/WskListen"
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 1703
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- wsk.h
api_name:
- WskListen
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFN_WSK_LISTEN callback function


## -description



   The <b>WskListen</b> function enables a stream socket to listen for incoming connections at the socket's bound address.


## -parameters




### -param Socket [in]

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/ns-wsk-_wsk_socket">WSK_SOCKET</a> structure that specifies the socket
     object for the stream socket that is listening for an incoming connection. This socket must have previously been bound to a local transport address by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nc-wsk-pfn_wsk_bind">WskBind</a>.


### -param Irp [in, out]

A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the listen operation
     asynchronously. For more information about using IRPs with WSK functions, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/using-irps-with-winsock-kernel-functions">Using IRPs with Winsock
     Kernel Functions</a>.


## -returns



<b>WskListen</b> returns one of the following NTSTATUS codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The stream socket listened for an incoming connection successfully. The IRP will be completed with success
       status.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The IRP has been queued by the WSK subsystem, which is waiting for an incoming connection on the
       stream socket.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FILE_FORCED_CLOSED</b></dt>
</dl>
</td>
<td width="60%">
The socket is no longer functional. The IRP will be completed with failure status. The WSK
       application must call the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nc-wsk-pfn_wsk_close_socket">WskCloseSocket</a> function to close the
       socket as soon as possible.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred. The IRP will be completed with failure status.

</td>
</tr>
</table>
 




## -remarks



A WSK application can call the <b>WskListen</b> function only on a stream socket that the application previously bound to a local transport address by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nc-wsk-pfn_wsk_bind">WskBind</a> function. Once <b>WskListen</b> is successfully called on a stream socket, the socket is committed to a listening socket flow and can no longer call connection-oriented socket functions.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/ns-wsk-_wsk_provider_stream_dispatch">WSK_PROVIDER_STREAM_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/ns-wsk-_wsk_socket">WSK_SOCKET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nc-wsk-pfn_wsk_accept">WskAccept</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nc-wsk-pfn_wsk_bind">WskBind</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nc-wsk-pfn_wsk_close_socket">WskCloseSocket</a>
 

 

