---
UID: NF:fwpsk.FwpsCompleteOperation0
title: FwpsCompleteOperation0 function
author: windows-driver-content
description: The FwpsCompleteOperation0 function is called by a callout to resume packet processing that was suspended pending completion of another operation.Note  FwpsCompleteOperation0 is a specific version of FwpsCompleteOperation.
old-location: netvista\fwpscompleteoperation0.htm
old-project: netvista
ms.assetid: e0d584c4-ec58-4d5f-bddf-86bcfbfa6b97
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: FwpsCompleteOperation0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FwpsCompleteOperation0
req.alt-loc: fwpkclnt.lib,fwpkclnt.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsCompleteOperation0 function



## -description
The 
  <b>FwpsCompleteOperation0</b> function is called by a callout to resume packet processing that was suspended
  pending completion of another operation.



## -syntax

````
void NTAPI FwpsCompleteOperation0(
  _In_     HANDLE           completionContext,
  _In_opt_ PNET_BUFFER_LIST netBufferList
);
````


## -parameters

### -param completionContext [in]

A completion context handle that was previously created by a call to the 
     <a href="..\fwpsk\nf-fwpsk-fwpspendoperation0.md">FwpsPendOperation0</a> function.


### -param netBufferList [in, optional]

A pointer to a 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure that describes
     the packet data for which processing has been suspended pending completion of another operation.


## -returns
None.


## -remarks
When the callout is ready to resume packet processing after operations on the packet were suspended by
    a call to 
    <a href="..\fwpsk\nf-fwpsk-fwpspendoperation0.md">FwpsPendOperation0</a>, the callout should
    call the 
    <b>FwpsCompleteOperation0</b> function, passing it the 
    <i>completionContext</i> parameter value from 
    <b>FwpsPendOperation0</b> and the net buffer
    list data that describes the packet.

To complete a connection that was previously pended at the FWPS_LAYER_ALE_AUTH_RECV_ACCEPT_<i>Xxx</i> layer, the callout driver must reinject the packet that was cloned at that layer, and the
    callout should also call 
    <b>FwpsCompleteOperation0</b>.

Pended connections are authenticated again after the 
    <b>FwpsCompleteOperation0</b> function executes. TCP connections, if allowed, are created by completing
    the handshake operation, but non-TCP connections just create state entries. Any pended packet data
    is flushed from memory when the 
    <b>FwpsPendOperation0</b> function completes, so an application will have to retransmit those packets
    after 
    <b>FwpsCompleteOperation0</b> executes. The callout could buffer such data and reinject the data on the
    application's behalf.


## -see-also
<dl>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpspendoperation0.md">FwpsPendOperation0</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsCompleteOperation0 function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

