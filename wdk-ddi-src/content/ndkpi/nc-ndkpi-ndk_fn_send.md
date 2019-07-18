---
UID: NC:ndkpi.NDK_FN_SEND
title: NDK_FN_SEND (ndkpi.h)
description: The NdkSend (NDK_FN_SEND) function posts a send request on an NDK queue pair (QP).
old-location: netvista\ndk_fn_send.htm
tech.root: netvista
ms.assetid: 6EDF95F1-AE00-4931-9B18-E316D56D57AF
ms.date: 05/02/2018
ms.keywords: NDK_FN_SEND, NDK_FN_SEND callback, NDK_OP_FLAG_DEFER, NDK_OP_FLAG_INLINE, NDK_OP_FLAG_READ_FENCE, NDK_OP_FLAG_SEND_AND_SOLICIT_EVENT, NDK_OP_FLAG_SILENT_SUCCESS, NdkSend, NdkSend callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkSend, netvista.ndk_fn_send
ms.topic: callback
f1_keywords:
 - "ndkpi/NdkSend"
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- ndkpi.h
api_name:
- NdkSend
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDK_FN_SEND callback function


## -description


The <i>NdkSend</i> (<i>NDK_FN_SEND</i>) function posts a send request on an NDK queue pair (QP).


## -parameters




### -param *pNdkQp [in]

A pointer to an NDK queue pair (QP) object
(<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_qp">NDK_QP</a>).


### -param RequestContext [in, optional]

A context value to be returned in the <b>RequestContext</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_result">NDK_RESULT</a> structure for this request.



### -param NDK_SGE

An array of SGE structures (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_sge">NDK_SGE</a>)  that represent the buffers holding the data to send.


### -param nSge [in]

The number of SGE structures in the array  that is specified in the <i>pSgl</i>
parameter.


### -param Flags [in]

A bitwise OR of flags which specifies the operations that are allowed. The following flags are supported:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="NDK_OP_FLAG_SILENT_SUCCESS"></a><a id="ndk_op_flag_silent_success"></a><dl>
<dt><b>NDK_OP_FLAG_SILENT_SUCCESS</b></dt>
<dt>0x00000001</dt>
</dl>
</td>
<td width="60%">
Indicates the successful completion of this request does not generate a completion event in the outbound completion queue. However, requests that fail do generate an event in the completion queue.

</td>
</tr>
<tr>
<td width="40%"><a id="NDK_OP_FLAG_READ_FENCE"></a><a id="ndk_op_flag_read_fence"></a><dl>
<dt><b>NDK_OP_FLAG_READ_FENCE</b></dt>
<dt>0x00000002</dt>
</dl>
</td>
<td width="60%">
Indicates that all prior read requests must be complete before the hardware begins processing this request.

</td>
</tr>
<tr>
<td width="40%"><a id="NDK_OP_FLAG_SEND_AND_SOLICIT_EVENT"></a><a id="ndk_op_flag_send_and_solicit_event"></a><dl>
<dt><b>NDK_OP_FLAG_SEND_AND_SOLICIT_EVENT</b></dt>
<dt>0x00000004</dt>
</dl>
</td>
<td width="60%">
Indicates that the completion queue for the peer generates a notification. For more information about <b>NDK_OP_FLAG_SEND_AND_SOLICIT_EVENT</b>, see the Remarks section.

</td>
</tr>
<tr>
<td width="40%"><a id="NDK_OP_FLAG_INLINE"></a><a id="ndk_op_flag_inline"></a><dl>
<dt><b>NDK_OP_FLAG_INLINE</b></dt>
<dt>0x00000040</dt>
</dl>
</td>
<td width="60%">
Indicates that the memory referenced by the SGEs should be transferred inline.  Also, the <b>MemoryRegionToken</b> value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_sge">NDK_SGE</a> entries might be invalid. Inline requests do not need to limit the number of entries in the SGE list to the <b>MaxInitiatorRequestSge</b>  value that is specified when the queue pair was created. The amount of memory transferred inline must be within the inline data limits of the queue pair.

</td>
</tr>
<tr>
<td width="40%"><a id="NDK_OP_FLAG_DEFER"></a><a id="ndk_op_flag_defer"></a><dl>
<dt><b>NDK_OP_FLAG_DEFER</b></dt>
<dt>0x00000200</dt>
</dl>
</td>
<td width="60%">
Indicates to the NDK provider that it may defer indicating the request to hardware for processing. For more information about this flag, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndkpi-deferred-processing-scheme">NDKPI Deferred Processing Scheme</a>.

<b>Note</b>  This flag is supported only in NDKPI 1.2 (Windows Server 2012 R2) and later.

</td>
</tr>
</table>

## -returns



The 
     <i>NdkSend</i> function returns one of the following NTSTATUS codes.

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
The send request was posted successfully. A completion entry will be queued to the completion queue (CQ) when the work request is completed.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CONNECTION_INVALID</b></dt>
</dl>
</td>
<td width="60%">
The queue pair (QP) is not connected.

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



<i>NdkSend</i> posts a send request on a queue pair (QP).

You can use the <b>NDK_OP_FLAG_SEND_AND_SOLICIT_EVENT</b> flag if you issue multiple, related send requests. Set this flag on the last request in the group of related send requests.

An NDK consumer can use this flag when issuing multiple, related send requests. The NDK consumer sets this flag only on the last, related send request. The peer will receive all the send requests as normal. However, when the peer receives the last send request (the request with the <b>NDK_OP_FLAG_SEND_AND_SOLICIT_EVENT</b> flag set), the completion queue for the peer generates a notification. The notification is generated after the receive request completes. This flag has no meaning to the receiver (peer) unless the receiver has previously called the <i>NdkArmCq</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_arm_cq">NDK_FN_ARM_CQ</a>) function with the notification type set to <b>NDK_CQ_NOTIFY_SOLICITED</b>. 

<div class="alert"><b>Note</b>  Requests that complete  with an error always match the <b>NDK_CQ_NOTIFY_SOLICITED</b> notification type.</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndkpi-deferred-processing-scheme">NDKPI Deferred Processing Scheme</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndkpi-work-request-posting-requirements">NDKPI Work Request Posting Requirements</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_arm_cq">NDK_FN_ARM_CQ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_qp">NDK_QP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_result">NDK_RESULT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_sge">NDK_SGE</a>
 

 

