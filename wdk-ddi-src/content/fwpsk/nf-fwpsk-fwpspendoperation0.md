---
UID: NF:fwpsk.FwpsPendOperation0
title: FwpsPendOperation0 function
author: windows-driver-content
description: The FwpsPendOperation0 function is called by a callout to suspend packet processing pending completion of another operation.Note  FwpsPendOperation0 is a specific version of FwpsPendOperation.
old-location: netvista\fwpspendoperation0.htm
old-project: netvista
ms.assetid: 03423785-83c5-4908-8c06-3be1b226c29e
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: FwpsPendOperation0, FwpsPendOperation0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsPendOperation0, netvista.fwpspendoperation0, wfp_ref_2_funct_3_fwps_J-Q_4e19462a-e31a-4d06-af83-68b11a00dd7a.xml
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
-	Fwpkclnt.lib
-	Fwpkclnt.dll
api_name:
-	FwpsPendOperation0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsPendOperation0 function


## -description


The 
  <b>FwpsPendOperation0</b> function is called by a callout to suspend packet processing pending completion of
  another operation.
<div class="alert"><b>Note</b>  <b>FwpsPendOperation0</b> is a specific version of <b>FwpsPendOperation</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters




### -param completionHandle [in]

A completion handle that is required to pend the current filtering operation. This parameter is
     obtained from the 
     <b>completionHandle</b> member of the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff552397">FWPS_INCOMING_METADATA_VALUES0</a> structure passed into the callout driver's 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a> function.


### -param completionContext [out]

The handle to the completion context of this pend operation. When the callout is ready to resume
     packet processing, it calls the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff551152">FwpsCompleteOperation0</a> function
     with the value of this parameter as the input 
     <i>completionContext</i> parameter.


## -returns



The 
     <b>FwpsPendOperation0</b> function returns one of the following NTSTATUS codes.

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
Packet processing was successfully pended.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FWP_CANNOT_PEND</b></dt>
</dl>
</td>
<td width="60%">
A call was made to 
       <b>FwpsPendOperation0</b> in a reauthorization classify operation. For more information, see Remarks.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FWP_NULL_POINTER</b></dt>
</dl>
</td>
<td width="60%">
One or more of the parameters is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FWP_TCPIP_NOT_READY</b></dt>
</dl>
</td>
<td width="60%">
The TCP/IP network stack is not ready to allow this operation.

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



The callout should retain the 
    <i>completionContext</i> parameter value until it resumes packet processing. When the operation that
    prompted the call to this function has completed, the callout should call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551152">FwpsCompleteOperation0</a> function,
    passing it the 
    <i>completionContext</i> parameter value.

A callout can call this function only to pend a packet that originates from the
    FWPM_LAYER_ALE_RESOURCE_ASSIGNMENT_
    <i>Xxx</i>, FWPM_LAYER_ALE_AUTH_LISTEN_
    <i>Xxx</i>, or FWPM_LAYER_ALE_AUTH_CONNECT_
    <i>Xxx</i> <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/using-layer-2-filtering">filtering layers</a>. A callout can
    pend the current processing operation on a packet when the callout must perform processing on one of
    these layers that may take a long interval to complete or that should occur at IRQL = PASSIVE_LEVEL if
    the current IRQL &gt; PASSIVE_LEVEL.

To complete a connection that was previously pended at the FWPS_LAYER_ALE_AUTH_RECV_ACCEPT_
    <i>Xxx</i> layer, the callout driver must reinject the packet that was cloned at that layer as well as
    call the 
    <b>FwpsCompleteOperation0</b> function.

To be able to pend packet processing, the callout driver's 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a> function should set the 
    <b>actionType</b> member of the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551229">FWPS_CLASSIFY_OUT0</a> structure to
    FWP_ACTION_BLOCK and the 
    <b>Flags</b> member to FWPS_CLASSIFY_OUT_FLAG_ABSORB.

Pended connections are reauthenticated after the 
    <b>FwpsCompleteOperation0</b> function executes. TCP connections, if allowed, are created by completing
    the handshake operation, but non-TCP connections only create state entries. Any pended packet data
    is flushed from memory when the 
    <b>FwpsPendOperation0</b> function completes, so applications must retransmit those packets after 
    <b>FwpsCompleteOperation0</b> runs. Callouts could buffer such data and reinject the data on their
    behalf.

Only an initial Application Layer Enforcement (ALE) flow authorization can be postponed by calling 
    <b>FwpsPendOperation0</b> and 
    <b>FwpsCompleteOperation0</b>. If an ALE flow is reauthorized, the FWP_CONDITION_FLAG_IS_REAUTHORIZE flag
    is set. A call to 
    <b>FwpsPendOperation0</b> from the FWPM_LAYER_ALE_AUTH_CONNECT_
    <i>Xxx</i> or FWPM_LAYER_ALE_AUTH_RECV_ACCEPT_
    <i>Xxx</i> <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/using-layer-2-filtering">filtering layers</a> will fail if the
    FWP_CONDITION_FLAG_IS_REAUTHORIZE flag is set, and the STATUS_FWP_CANNOT_PEND status code will be
    returned. For more information, see ALE Reauthorization in the Windows SDK.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551229">FWPS_CLASSIFY_OUT0</a>



<a href="https://msdn.microsoft.com/fba7eb60-0d19-4bfd-b484-2e615d3e9237">
   FWPS_INCOMING_METADATA_VALUES0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551152">FwpsCompleteOperation0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsPendOperation0 function%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

