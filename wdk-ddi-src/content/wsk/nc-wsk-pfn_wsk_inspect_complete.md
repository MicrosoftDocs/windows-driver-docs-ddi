---
UID: NC:wsk.PFN_WSK_INSPECT_COMPLETE
title: PFN_WSK_INSPECT_COMPLETE
author: windows-driver-content
description: The WskInspectComplete function completes the inspection of a previously pended incoming connection request that was received on a listening socket that has conditional accept mode enabled.
old-location: netvista\wskinspectcomplete.htm
old-project: netvista
ms.assetid: 31846ec9-0a4b-4e1f-9c14-c1b139f39c55
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: PFN_WSK_INSPECT_COMPLETE, PFN_WSK_INSPECT_COMPLETE callback, WskInspectComplete, WskInspectComplete callback function [Network Drivers Starting with Windows Vista], netvista.wskinspectcomplete, wsk/WskInspectComplete, wskref_af7aebea-0be9-457d-8404-6106b21312ec.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	wsk.h
api_name:
-	WskInspectComplete
product: Windows
targetos: Windows
req.typenames: 
---

# PFN_WSK_INSPECT_COMPLETE callback function


## -description


The 
  <b>WskInspectComplete</b> function completes the inspection of a previously pended incoming connection
  request that was received on a listening socket that has conditional accept mode enabled.


## -parameters




### -param ListenSocket [in]

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571182">WSK_SOCKET</a> structure. This pointer specifies the
     listening socket on which the WSK application received the incoming connection request that it is
     inspecting.


### -param InspectID [in]

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571170">WSK_INSPECT_ID</a> structure. The contents of
     the structure identify the specific connection request that the WSK application is inspecting.


### -param Action [in]

A value that specifies whether the WSK application accepts or rejects the incoming connection
     request. A WSK application must specify either 
     <b>WskInspectAccept</b> or 
     <b>WskInspectReject</b> for this parameter.


### -param Irp [in, out]

A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the resume operation
     asynchronously. For more information about using IRPs with WSK functions, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/using-irps-with-winsock-kernel-functions">Using IRPs with Winsock
     Kernel Functions</a>.


## -returns



<b>WskInspectComplete</b> returns one of the following NTSTATUS codes:

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
The previously pended inspect operation was successfully resumed. The IRP will be completed with
       success status.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The WSK subsystem could not resume the inspect operation immediately. The WSK subsystem will
       complete the IRP after it has resumed the inspect operation of the incoming connection request. The
       status of resuming the inspect operation will be returned in the 
       <b>IoStatus.Status</b> field of the IRP.

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
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff571124">WskCloseSocket</a> function to close the
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



A WSK application calls the 
    <b>WskInspectComplete</b> function to complete the inspection of an incoming connection request for which
    the application's 
    <a href="https://msdn.microsoft.com/40f184ac-4ef3-485a-a529-71c1f2716427">WskInspectEvent</a> event callback function
    previously returned 
    <b>WskInspectPend</b>.

A WSK application can call the 
    <b>WskInspectComplete</b> function only on a listening socket that has conditional accept mode enabled. A
    WSK application can enable conditional accept mode on a listening socket by enabling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff570829">SO_CONDITIONAL_ACCEPT</a> socket option.
    For more information about conditionally accepting incoming connections, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/listening-for-and-accepting-incoming-connections">Listening for and
    Accepting Incoming Connections</a>.

The WSK subsystem passed a pointer to a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571170">WSK_INSPECT_ID</a> structure to the WSK
    application when it called the application's 
    <i>WskInspectEvent</i> event callback function. The WSK application copied the contents of that structure
    to its own WSK_INSPECT_ID structure before returning 
    <b>WskInspectPend</b> from the 
    <i>WskInspectEvent</i> event callback function. The WSK application passes a pointer to its own
    WSK_INSPECT_ID structure in the 
    <i>InspectID</i> parameter when it calls the 
    <b>WskInspectComplete</b> function.

If a WSK application specifies 
    <b>WskInspectAccept</b> in the 
    <i>Action</i> parameter, the WSK subsystem will continue to establish the socket connection. The WSK
    subsystem will return the socket to the WSK application by either completing a call by the WSK
    application to the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571109">WskAccept</a> function or calling the WSK
    application's 
    <a href="https://msdn.microsoft.com/672440f0-810a-4e68-82a5-d038770898c5">WskAcceptEvent</a> event callback function if
    it is enabled. If the incoming connection request is dropped before the socket connection is fully
    established, the WSK subsystem will call the WSK application's 
    <a href="https://msdn.microsoft.com/50e0ef5d-0577-4b5c-b541-fc78079a953c">WskAbortEvent</a> event callback function.

If a WSK application specifies 
    <b>WskInspectReject</b> in the 
    <i>Action</i> parameter, the incoming connection request is dropped, and the socket connection is not
    established.

If the incoming connection request is dropped by the remote system before the WSK application calls
    the 
    <b>WskInspectComplete</b> function, the WSK subsystem calls the WSK application's 
    <i>WskAbortEvent</i> event callback function.

If the WSK application calls the 
    <b>WskInspectComplete</b> function on an incoming connection request that has been aborted, the connection
    will not be established even if the WSK application specified 
    <b>WskInspectAccept</b> in the 
    <i>Action</i> parameter.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570829">SO_CONDITIONAL_ACCEPT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571170">WSK_INSPECT_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571176">WSK_PROVIDER_LISTEN_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571182">WSK_SOCKET</a>



<a href="https://msdn.microsoft.com/50e0ef5d-0577-4b5c-b541-fc78079a953c">WskAbortEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571109">WskAccept</a>



<a href="https://msdn.microsoft.com/672440f0-810a-4e68-82a5-d038770898c5">WskAcceptEvent</a>



<a href="https://msdn.microsoft.com/40f184ac-4ef3-485a-a529-71c1f2716427">WskInspectEvent</a>
 

 

