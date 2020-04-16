---
UID: NF:fwpsk.FwpsCompleteOperation0
title: FwpsCompleteOperation0 function (fwpsk.h)
description: The FwpsCompleteOperation0 function is called by a callout to resume packet processing that was suspended pending completion of another operation.Note  FwpsCompleteOperation0 is a specific version of FwpsCompleteOperation.
old-location: netvista\fwpscompleteoperation0.htm
tech.root: netvista
ms.assetid: e0d584c4-ec58-4d5f-bddf-86bcfbfa6b97
ms.date: 05/02/2018
keywords: ["FwpsCompleteOperation0 function"]
ms.keywords: FwpsCompleteOperation0, FwpsCompleteOperation0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsCompleteOperation0, netvista.fwpscompleteoperation0, wfp_ref_2_funct_3_fwps_C_bfabbf4d-812a-411f-b9ef-c2e6f145404d.xml
f1_keywords:
 - "fwpsk/FwpsCompleteOperation0"
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- fwpkclnt.lib
- fwpkclnt.dll
api_name:
- FwpsCompleteOperation0
product:
- Windows
targetos: Windows
req.typenames: 
---

# FwpsCompleteOperation0 function


## -description


The 
  <b>FwpsCompleteOperation0</b> function is called by a callout to resume packet processing that was suspended
  pending completion of another operation.
<div class="alert"><b>Note</b>  <b>FwpsCompleteOperation0</b> is a specific version of <b>FwpsCompleteOperation</b>. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters




### -param completionContext [in]

A completion context handle that was previously created by a call to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpspendoperation0">FwpsPendOperation0</a> function.


### -param netBufferList [in, optional]

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure that describes
     the packet data for which processing has been suspended pending completion of another operation.


## -remarks



When the callout is ready to resume packet processing after operations on the packet were suspended by
    a call to 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpspendoperation0">FwpsPendOperation0</a>, the callout should
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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpspendoperation0">FwpsPendOperation0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>
 

 

