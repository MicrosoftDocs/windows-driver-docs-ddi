---
UID: NF:fwpsk.FwpsInjectionHandleCreate0
title: FwpsInjectionHandleCreate0 function (fwpsk.h)
description: The FwpsInjectionHandleCreate0 function creates a handle that can be used by packet injection functions to inject packet or stream data into the TCP/IP network stack and by the FwpsQueryPacketInjectionState0 function to query the packet injection state.Note  FwpsInjectionHandleCreate0 is a specific version of FwpsInjectionHandleCreate. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information.
old-location: netvista\fwpsinjectionhandlecreate0.htm
tech.root: netvista
ms.assetid: 61cee8ef-1070-46d4-a541-94a9f09b593b
ms.date: 05/02/2018
keywords: ["FwpsInjectionHandleCreate0 function"]
ms.keywords: FwpsInjectionHandleCreate0, FwpsInjectionHandleCreate0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsInjectionHandleCreate0, netvista.fwpsinjectionhandlecreate0, wfp_ref_2_funct_3_fwps_I_24f21d21-bf9c-4f77-9630-2c589b18aca4.xml
f1_keywords:
 - "fwpsk/FwpsInjectionHandleCreate0"
 - "FwpsInjectionHandleCreate0"
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- fwpkclnt.lib
- fwpkclnt.dll
api_name:
- FwpsInjectionHandleCreate0
targetos: Windows
req.typenames: 
---

# FwpsInjectionHandleCreate0 function


## -description


The 
  <b>FwpsInjectionHandleCreate0</b> function creates a handle that can be used by 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/network/packet-injection-functions">packet injection functions</a> to inject
  packet or stream data into the TCP/IP network stack and by the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsquerypacketinjectionstate0">FwpsQueryPacketInjectionState0</a> function to query the packet injection state.
<div class="alert"><b>Note</b>  <b>FwpsInjectionHandleCreate0</b> is a specific version of <b>FwpsInjectionHandleCreate</b>. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters




### -param addressFamily 
[in, optional]
The address family for which the injection handle is being created. This can be one of the
     following address families:
     





#### AF_UNSPEC

The address family is unspecified.



#### AF_INET

The IPv4 address family.



#### AF_INET6

The IPv6 address family.

For transport, stream, and forward injections, this parameter is optional and can be set to
     AF_UNSPEC, which indicates an unspecified address family. This value is defined in 
     Ws2def.h.


### -param flags 
[in]
A flag value set by a callout driver to indicate the type of data to be injected. This flag can have
     one or more of the following values: 
     





#### FWPS_INJECTION_TYPE_FORWARD

Packet data will be injected by calling the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsinjectforwardasync0">
       FwpsInjectForwardAsync0</a> function.



#### FWPS_INJECTION_TYPE_NETWORK

Network data will be injected by calling either the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsinjectnetworkreceiveasync0">
       FwpsInjectNetworkReceiveAsync0</a> function or the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsinjectnetworksendasync0">
       FwpsInjectNetworkSendAsync0</a> function.



#### FWPS_INJECTION_TYPE_STREAM

Stream data will be injected by calling the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsstreaminjectasync0">
       FwpsStreamInjectAsync0</a> function.



#### FWPS_INJECTION_TYPE_TRANSPORT

Transport data will be injected by calling either the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsinjecttransportreceiveasync0">
       FwpsInjectTransportReceiveAsync0</a> function or the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsinjecttransportsendasync0">
       FwpsInjectTransportSendAsync0</a> function.

 To create an injection handle to be used by multiple injection functions, combine the
     injection type bits with bitwise OR operations. If the flag value is set to zero, the resulting
     injection handle can be used for transport, stream, and forward injections.


### -param injectionHandle 
[out]
A pointer to a variable that receives the handle.


## -returns



The 
     <b>FwpsInjectionHandleCreate0</b> function returns one of the following NTSTATUS codes.

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
The injection handle was successfully created.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FWP_TCPIP_NOT_READY</b></dt>
</dl>
</td>
<td width="60%">
The TCP/IP network stack is not ready. A callout driver should call the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsinjectionhandlecreate0">FwpsInjectionHandleCreate0</a> function again at a later time to create an injection handle.

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
    <b>FwpsInjectionHandleCreate0</b> function to create a handle that can be used for injecting packet or
    stream data into the TCP/IP network stack and to query the packet injection state. A callout driver
    passes the created handle to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/packet-injection-functions">packet injection
    functions</a> and 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsquerypacketinjectionstate0">
    FwpsQueryPacketInjectionState0</a>.

After a callout driver has finished using an injection handle, it must call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsinjectionhandledestroy0">FwpsInjectionHandleDestroy0</a> function to destroy the handle. If pending injections have not yet
    completed, this function will wait for their completion before returning.

When injections are being made to the network layer and both IPv4 and IPv6 address families are being
    filtered, the callout driver must create two injection handles by calling the 
    <b>FwpsInjectionHandleCreate0</b> function twice: one call with 
    <i>addressFamily</i> set to AF_INET, and a second call with 
    <i>addressFamily</i> set to AF_INET6.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsinjectionhandledestroy0">FwpsInjectionHandleDestroy0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsquerypacketinjectionstate0">
   FwpsQueryPacketInjectionState0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/packet-injection-functions">Packet Injection Functions</a>
 

 

