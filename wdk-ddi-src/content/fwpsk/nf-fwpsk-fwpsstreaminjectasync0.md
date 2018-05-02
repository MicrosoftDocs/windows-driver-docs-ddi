---
UID: NF:fwpsk.FwpsStreamInjectAsync0
title: FwpsStreamInjectAsync0 function
author: windows-driver-content
description: The FwpsStreamInjectAsync0 function injects TCP data segments into a TCP data stream.Note  FwpsStreamInjectAsync0 is a specific version of FwpsStreamInjectAsync.
old-location: netvista\fwpsstreaminjectasync0.htm
old-project: netvista
ms.assetid: d72c3067-21df-40ee-a898-100fcdc5eaca
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: FwpsStreamInjectAsync0, FwpsStreamInjectAsync0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsStreamInjectAsync0, netvista.fwpsstreaminjectasync0, wfp_ref_2_funct_3_fwps_R-Z_422b8f08-5d55-4825-8c17-62c4c4e2c1c1.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	fwpkclnt.lib
-	fwpkclnt.dll
api_name:
-	FwpsStreamInjectAsync0
product:
- Windows
targetos: Windows
req.typenames: 
---

# FwpsStreamInjectAsync0 function


## -description


The 
  <b>FwpsStreamInjectAsync0</b> function injects TCP data segments into a TCP data stream.
<div class="alert"><b>Note</b>  <b>FwpsStreamInjectAsync0</b> is a specific version of <b>FwpsStreamInjectAsync</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters




### -param injectionHandle [in]

An injection handle that was previously created by a call to the 
     <a href="https://msdn.microsoft.com/61cee8ef-1070-46d4-a541-94a9f09b593b">
     FwpsInjectionHandleCreate0</a> function.


### -param injectionContext [in, optional]

An optional handle to the injection context.


### -param flags [in]

Reserved. Callout drivers should set this parameter to zero.


### -param flowId [in]

A run-time identifier that specifies the data flow into which to inject the data. The run-time
     identifier for a data flow is provided to a callout driver through the FWPS_METADATA_FIELD_FLOW_HANDLE
     metadata value that the filter engine provided to the callout driver's 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a> callout function.


### -param calloutId [in]

The run-time identifier for the callout in the filter engine. This identifier was returned when
     the callout driver called either the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff551140">FwpsCalloutRegister0</a> or 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff551143">FwpsCalloutRegister1</a> functions to
     register the callout with the filter engine.


### -param layerId [in]

The run-time identifier for the filtering layer at which the data stream is being processed. This
     value must be either FWPS_LAYER_STREAM_V4 or FWPS_LAYER_STREAM_V6. The run-time identifier for the layer
     at which the data stream is being processed is provided to a callout in the 
     <b>layerId</b> member of the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff552401">FWPS_INCOMING_VALUES0</a> structure that
     the filter engine passed to the callout driver's 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a> callout function.


### -param streamFlags [in]

Flags that specify characteristics of the data stream into which the data is to be injected.
     

When injecting data into an inbound data stream, a callout driver specifies one or more of the
     following flags:





#### FWPS_STREAM_FLAG_RECEIVE

Specifies that the data is to be injected into the inbound data stream. This flag is required
       when injecting data into an inbound data stream.



#### FWPS_STREAM_FLAG_RECEIVE_DISCONNECT

Specifies that the FIN flag is to be set in the TCP header for the data being injected into the
       inbound data stream.

<div class="alert"><b>Note</b>  If this flag is set, the <b>FWPS_STREAM_FLAG_RECEIVE</b> flag must also be set, or else <b>STATUS_FWP_INVALID_PARAMETER</b> will be returned.</div>
<div> </div>


#### FWPS_STREAM_FLAG_RECEIVE_EXPEDITED

Specifies that the data being injected into the inbound data stream is high-priority,
       out-of-band data.



#### FWPS_STREAM_FLAG_RECEIVE_PUSH

Specifies that the inbound data has arrived with the PUSH flag set in the TCP header, which
       indicates that the sender requests immediate data transfer. Unwanted delays in data transfer can occur
       if this flag is not set. This flag is available starting with Windows Vista with SP1.

When injecting data into an outbound data stream, a callout driver specifies one or more of the
     following flags:





#### FWPS_STREAM_FLAG_SEND

Specifies that the data is to be injected into the outbound data stream. This flag is required
       when injecting data into an outbound data stream.



#### FWPS_STREAM_FLAG_SEND_EXPEDITED

Specifies that the data being injected into the outbound data stream is high-priority,
       out-of-band data.



#### FWPS_STREAM_FLAG_SEND_NODELAY

Specifies that the callout driver requests that there is no buffering of the data being injected
       into the outbound data stream.



#### FWPS_STREAM_FLAG_SEND_DISCONNECT

Specifies that the stream is to be disconnected after the data being injected into the outbound
       data stream has been sent. The network stack will set the FIN flag in the TCP header of the last
       packet that is sent out.

<div class="alert"><b>Note</b>  If this flag is set, the <b>FWPS_STREAM_FLAG_SEND</b> flag must also be set, or else <b>STATUS_FWP_INVALID_PARAMETER</b> will be returned.</div>
<div> </div>

### -param netBufferList [in, out]

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure that describes
     the data that is being injected into the data stream. A callout driver allocates a <b>NET_BUFFER_LIST</b>
     structure to use for injecting data into a data stream by calling the 
     <a href="https://msdn.microsoft.com/72759748-fac6-45b9-9a81-ab71e6e7c3ef">
     FwpsAllocateCloneNetBufferList0</a>, 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff551135">FwpsAllocateNetBufferAndNetBufferList0</a>, or 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff551149">FwpsCloneStreamData0</a> functions. The
     <b>NET_BUFFER_LIST</b> structure can describe a chain of network buffer lists. If the 
     <i>streamFlags</i> parameter is <b>FWPS_STREAM_FLAG_RECEIVE_DISCONNECT</b> or <b>FWPS_STREAM_FLAG_SEND_DISCONNECT</b>, 
     <i>netBufferList</i> can be <b>NULL</b>.


### -param dataLength [in]

The number of bytes of data being injected into the data stream.


### -param completionFn [in]

A pointer to a 
     <a href="https://msdn.microsoft.com/c03656ec-f0fe-49f5-8a04-2d26ef23c50a">completionFn</a> callout function provided by
     the callout driver. The filter engine calls this function after the packet data, described by the 
     <i>netBufferList</i> parameter, has been injected into the network stack. 

If the 
     <i>netBufferList</i> parameter describes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> chain, 
     <i>completionFn</i> will be called once for each <b>NET_BUFFER_LIST</b> in the chain.

If the 
     <i>netBufferList</i> parameter is <b>NULL</b>  and the 
     <i>streamFlags</i> parameter has either <b>FWPS_STREAM_FLAG_RECEIVE_DISCONNECT</b> or <b>FWPS_STREAM_FLAG_SEND_DISCONNECT</b> set, the <a href="https://msdn.microsoft.com/c03656ec-f0fe-49f5-8a04-2d26ef23c50a">completionFn</a> function will not be called.

This parameter is required and cannot be <b>NULL</b>. If it is <b>NULL</b>, <b>STATUS_FWP_NULL_POINTER</b> will be returned.


### -param completionContext [in, optional]

A pointer to a callout driver–provided context that is passed to the callout function pointed to
     by the 
     <i>completionFn</i> parameter. This parameter is optional and can be <b>NULL</b>.


## -returns



The 
     <b>FwpsStreamInjectAsync0</b> function an NTSTATUS code such as one of the following.

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
The injection into the data stream was initiated successfully. The filter engine will call the
       completion function that was specified when the 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure was allocated
       after the filter engine has completed injecting the data into the data stream.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FWP_TCPIP_NOT_READY</b></dt>
</dl>
</td>
<td width="60%">
The TCP/IP network stack is not ready to accept injection of stream data.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FWP_INJECT_HANDLE_CLOSING</b></dt>
</dl>
</td>
<td width="60%">
The injection handle is being closed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred.

</td>
</tr>
</table>
 




## -remarks



A callout driver calls the 
    <b>FwpsStreamInjectAsync0</b> function from within a callout's 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a> callout function to inject new
    or cloned data into the data stream that is currently being processed. A callout driver can call the
    FwpsStreamInjectAsync0 function only if it is processing a data flow at the stream layer.

A callout driver can also call the 
    <b>FwpsStreamInjectAsync0</b> function from outside of a callout's 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a> callout function to inject data into a data stream that is currently deferred. A data
    stream is deferred when a callout's 
    <i>classifyFn</i> callout function sets the 
    <b>streamAction</b> member of the 
    <a href="https://msdn.microsoft.com/2c0539f0-116e-4344-9584-db7416d258e0">
    FWPS_STREAM_CALLOUT_IO_PACKET0</a> structure to FWPS_STREAM_ACTION_DEFER.

In addition, a callout driver can call the 
    <b>FwpsStreamInjectAsync0</b> function from outside of a callout's 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a> callout function to inject data into a data stream after a FIN indication has been
    pended.

Alternately, a callout driver can call the 
    <b>FwpsStreamInjectAsync0</b> function from an arbitrary thread context outside a callout's 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a> callout function if the callout driver clones and blocks all data indicated for
    out-of-band processing. A callout driver that redirects all indicated data to user mode for processing
    can call the 
    <b>FwpsStreamInjectAsync0</b> function in this way.

A callout can pend a data segment by first cloning it with a call to the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551149">FwpsCloneStreamData0</a> function,
    followed by blocking the data segment by setting FWP_ACTION_BLOCK in the 
    <b>actionType</b> member of the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551229">FWPS_CLASSIFY_OUT0</a> structure.

Injected stream data will not be reindicated to the callout, but it will be made available to stream
    callouts from lower-weight sublayers.

If the return value is not STATUS_SUCCESS, the completion function will not be called. In this case,
    the network buffer list pointed to by 
    <i>metBufferList</i> must be freed by a call to 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551172">FwpsFreeNetBufferList0</a> or 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551170">FwpsFreeCloneNetBufferList0</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552401">FWPS_INCOMING_VALUES0</a>



<a href="https://msdn.microsoft.com/2c0539f0-116e-4344-9584-db7416d258e0">
   FWPS_STREAM_CALLOUT_IO_PACKET0</a>



<a href="https://msdn.microsoft.com/72759748-fac6-45b9-9a81-ab71e6e7c3ef">
   FwpsAllocateCloneNetBufferList0</a>



<a href="https://msdn.microsoft.com/d7f2d3c0-f2c9-4624-b3e1-9fbbf64c7186">
   FwpsAllocateNetBufferAndNetBufferList0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551140">FwpsCalloutRegister0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551143">FwpsCalloutRegister1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551149">FwpsCloneStreamData0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551180">FwpsInjectionHandleCreate0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551181">FwpsInjectionHandleDestroy0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a>



<a href="https://msdn.microsoft.com/c03656ec-f0fe-49f5-8a04-2d26ef23c50a">completionFn</a>
 

 

