---
UID: NC:wsk.PFN_WSK_RECEIVE_EVENT
title: PFN_WSK_RECEIVE_EVENT
author: windows-driver-content
description: The WskReceiveEvent event callback function notifies a WSK application that data has been received on a connection-oriented socket.
old-location: netvista\wskreceiveevent.htm
old-project: netvista
ms.assetid: 2a7a7570-ed26-48be-b27b-dc240588ecfc
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: PFN_WSK_RECEIVE_EVENT, PFN_WSK_RECEIVE_EVENT callback, WSK_FLAG_AT_DISPATCH_LEVEL, WSK_FLAG_ENTIRE_MESSAGE, WSK_FLAG_RELEASE_ASAP, WskReceiveEvent, WskReceiveEvent callback function [Network Drivers Starting with Windows Vista], netvista.wskreceiveevent, wsk/WskReceiveEvent, wskref_acb47379-99e4-42b8-92a1-19395cc29fd8.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Windows
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
-	WskReceiveEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFN_WSK_RECEIVE_EVENT callback function


## -description


The 
  <i>WskReceiveEvent</i> event callback function notifies a WSK application that data has been received on a
  connection-oriented socket.


## -parameters




### -param SocketContext [in, optional]

A pointer to the socket context for the connection-oriented socket that has received the data. The
     WSK application provided this pointer to the WSK subsystem in one of the following ways:
     

<ul>
<li>
It called the 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff571149">WskSocket</a> function to create the socket.

</li>
<li>
It called the 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff571150">WskSocketConnect</a> function to create
       the socket.

</li>
<li>
It called the 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff571109">WskAccept</a> function to accept the socket as an
       incoming connection.

</li>
<li>
Its 
       <a href="https://msdn.microsoft.com/672440f0-810a-4e68-82a5-d038770898c5">WskAcceptEvent</a> event callback function
       was called to accept the socket as an incoming connection.

</li>
</ul>

### -param Flags [in]

A ULONG value that contains a bitwise OR of a combination of the following flags:
     

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="WSK_FLAG_RELEASE_ASAP"></a><a id="wsk_flag_release_asap"></a><dl>
<dt><b>WSK_FLAG_RELEASE_ASAP</b></dt>
</dl>
</td>
<td width="60%">
The data buffers that contain the received data should not be retained by the WSK application if
       at all possible. If the WSK application retains the buffers, it should release them as soon as
       possible by calling the 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff571144">WskRelease</a> function.

</td>
</tr>
<tr>
<td width="40%"><a id="WSK_FLAG_ENTIRE_MESSAGE"></a><a id="wsk_flag_entire_message"></a><dl>
<dt><b>WSK_FLAG_ENTIRE_MESSAGE</b></dt>
</dl>
</td>
<td width="60%">
The data buffers contain either an entire message or the final portion of a message. The
       interpretation of what constitutes an entire message is transport protocol-specific. For TCP, this
       flag indicates that the push bit was set for one or more of the TCP segments that constitute the data
       in the data buffers.

</td>
</tr>
<tr>
<td width="40%"><a id="WSK_FLAG_AT_DISPATCH_LEVEL"></a><a id="wsk_flag_at_dispatch_level"></a><dl>
<dt><b>WSK_FLAG_AT_DISPATCH_LEVEL</b></dt>
</dl>
</td>
<td width="60%">
The WSK subsystem called the 
       <i>WskReceiveEvent</i> event callback function at IRQL = DISPATCH_LEVEL. If this flag is not set, the
       WSK subsystem might have called the 
       <i>WskReceiveEvent</i> event callback function at any IRQL &lt;= DISPATCH_LEVEL.

</td>
</tr>
</table>
 


### -param DataIndication [in, optional]

A pointer to a linked list of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571165">WSK_DATA_INDICATION</a> structures that
     describe the received data. If this parameter is <b>NULL</b>, the socket is no longer functional and the WSK
     application must call the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571124">WskCloseSocket</a> function to close the
     socket as soon as possible.


### -param BytesIndicated [in]

The number of bytes of received data described by the linked list of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571165">WSK_DATA_INDICATION</a> structures.


### -param *BytesAccepted [in, out]

A pointer to a SIZE_T-typed variable which receives the number of bytes of received data that is
     accepted by the WSK application. This variable needs to be set only if the WSK application accepts a
     portion of the total number of bytes of received data. If the WSK application accepts all of the
     received data, it does not have to set this variable. If the 
     <i>WskReceiveEvent</i> event callback function returns a status other than STATUS_SUCCESS, the WSK
     subsystem ignores the value of this variable.


## -returns



A WSK application's 
     <i>WskReceiveEvent</i> event callback function can return one of the following NTSTATUS codes:

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
The WSK application accepted at least some of the received data. If the WSK application accepted
       all of the received data, the WSK subsystem can call the 
       <i>WskReceiveEvent</i> event callback function again when new data is received on the socket. However,
       if the WSK application accepted only a portion of the received data, the WSK subsystem will not call
       the 
       <i>WskReceiveEvent</i> event callback function again until after the WSK application calls the 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff571139">WskReceive</a> function. After the WSK
       application calls the 
       <b>WskReceive</b> function, the WSK subsystem will resume calling the 
       <i>WskReceiveEvent</i> event callback function with any remaining buffered data and when new data is
       received on the socket. A WSK application can call the 
       <b>WskReceive</b> function with a zero-length buffer, which will cause the WSK subsystem to resume
       calling the 
       <i>WskReceiveEvent</i> event callback function without calling 
       <b>WskReceive</b> to receive any data from the socket.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The WSK application accepted the data but did not retrieve all of the data contained in the
       linked list of 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff571165">WSK_DATA_INDICATION</a> structures. The
       WSK application retains the linked list of WSK_DATA_INDICATION structures until all of the data has
       been retrieved. After the WSK application has retrieved all of the data it calls the 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff571144">WskRelease</a> function to release the linked
       list of WSK_DATA_INDICATION structures back to the WSK subsystem. The WSK subsystem can call the 
       <i>WskReceiveEvent</i> event callback function again when new data is received on the socket.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DATA_NOT_ACCEPTED</b></dt>
</dl>
</td>
<td width="60%">
The WSK application did not accept the data. In this situation, the WSK subsystem will have the
       underlying transport buffer the data if possible or if otherwise required by the protocol. The WSK
       subsystem will not call the 
       <i>WskReceiveEvent</i> event callback function again until after the WSK application calls the 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff571139">WskReceive</a> function. After the WSK
       application calls the 
       <b>WskReceive</b> function, the WSK subsystem will resume calling the 
       <i>WskReceiveEvent</i> event callback function with any remaining buffered data and when new data is
       received on the socket. A WSK application can call the 
       <b>WskReceive</b> function with a zero-length buffer, which will cause the WSK subsystem to resume
       calling the 
       <i>WskReceiveEvent</i> event callback function without calling 
       <b>WskReceive</b> to receive any data from the socket.

</td>
</tr>
</table>
 




## -remarks



The WSK subsystem calls a WSK application's 
    <i>WskReceiveEvent</i> event callback function when new data is received on a connection-oriented socket
    only if the event callback function was previously enabled with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff570834">SO_WSK_EVENT_CALLBACK</a> socket option.
    For more information about enabling a socket's event callback functions, see 
    <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/aa363707">Enabling and
    Disabling Event Callback Functions</a>.

If a WSK application's 
    <i>WskReceiveEvent</i> event callback function is enabled on a connection-oriented socket and the
    application also has a pending call to the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571139">WskReceive</a> function on the same
    connection-oriented socket, then, when data arrives, the pending call to the 
    <b>WskReceive</b> function will take precedence over the 
    <i>WskReceiveEvent</i> event callback function. The WSK subsystem calls the application's 
    <i>WskReceiveEvent</i> event callback function only if there are no IRPs queued from pending calls to the 
    <b>WskReceive</b> function. However, a WSK application should not assume that the WSK subsystem will not
    call the application's 
    <i>WskReceiveEvent</i> event callback function for a connection-oriented socket that has a pending call to
    the 
    <b>WskReceive</b> function. Race conditions exist where the WSK subsystem could still call the WSK
    application's 
    <i>WskReceiveEvent</i> event callback function for the socket. The only way for a WSK application to
    ensure that the WSK subsystem will not call the application's 
    <i>WskReceiveEvent</i> event callback function for a connection-oriented socket is to disable the
    application's 
    <i>WskReceiveEvent</i> event callback function on the socket.

The WSK subsystem calls a WSK application's 
    <i>WskReceiveEvent</i> event callback function at IRQL &lt;= DISPATCH_LEVEL.

A WSK application's <i>WskReceiveEvent</i> event callback function must not wait for completion of other WSK requests in the context of WSK completion or event callback functions. The callback can initiate other WSK requests (assuming that it doesn't spend too much time at DISPATCH_LEVEL), but it must not wait for their completion even when the callback is called at IRQL = PASSIVE_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/960eee8a-2950-4baf-b32d-be13b3d65951">
   WSK_CLIENT_CONNECTION_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571165">WSK_DATA_INDICATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571109">WskAccept</a>



<a href="https://msdn.microsoft.com/672440f0-810a-4e68-82a5-d038770898c5">WskAcceptEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571124">WskCloseSocket</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571139">WskReceive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571144">WskRelease</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571146">WskSend</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571149">WskSocket</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571150">WskSocketConnect</a>
 

 

