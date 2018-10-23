---
UID: NC:mrx.PMRX_CREATE_V_NET_ROOT
title: PMRX_CREATE_V_NET_ROOT
author: windows-driver-content
description: The MRxCreateVNetRoot routine is called by RDBSS to request that the network mini-redirector create a V_NET_ROOT structure and, in some cases, a NET_ROOT structure.
old-location: ifsk\mrxcreatevnetroot.htm
tech.root: ifsk
ms.assetid: 8cd5aa01-c814-4737-9088-0361e6ee9a61
ms.date: 04/16/2018
ms.keywords: MRxCreateVNetRoot, MRxCreateVNetRoot routine [Installable File System Drivers], PMRX_CREATE_V_NET_ROOT, ifsk.mrxcreatevnetroot, mrx/MRxCreateVNetRoot, mrxref_8d77acec-f7a5-40c6-8543-421c5c1f79f5.xml
ms.topic: callback
req.header: mrx.h
req.include-header: Mrx.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	mrx.h
api_name:
-	MRxCreateVNetRoot
product:
- Windows
targetos: Windows
req.typenames: 
---

# PMRX_CREATE_V_NET_ROOT callback function


## -description


The<i> MRxCreateVNetRoot</i> routine is called by <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that the network mini-redirector create a V_NET_ROOT structure and, in some cases, a NET_ROOT structure. 


## -parameters




### -param Context








#### - pCreateNetRootContext [in, out]

A pointer to the callback context used by the network mini-redirector to notify RDBSS when the call is finally completed. This includes the RX_CONTEXT structure of the request at <b>pCreateNetRootContext-&gt;RxContext</b>. The <i>pCreateNetRootContext</i> parameter includes the V_NET_ROOT structure to be constructed at <b>pCreateNetRootContext-&gt;pVNetRoot</b>. This V_NET_ROOT structure contains a pointer to the NET_ROOT structure at <b>pVNetRoot-&gt;pNetRoot</b>. The NET_ROOT structure also contains a pointer to the SRV_CALL structure at <b>pNetRoot-&gt;pSrvCall</b>.


## -returns



RDBSS expects that <i>MRxCreateVNetRoot</i> returns STATUS_PENDING on success or failure. This behavior results because RDBSS expects this call to be completed asynchronously. A network mini-redirector should map STATUS_SUCCESS to STATUS_PENDING as a return value for <i>MRxCreateVNetRoot</i>.

The final completion status is returned in <b>pCreateNetRootContext-&gt;VirtualNetRootStatus</b> and <b>pCreateNetRootContext-&gt;NetRootStatus</b> members once the call completes and the routine in the <b>Callback</b> member of <b>pCreateNetRootContext</b> structure is called by the network mini-redirector. These members initially contain STATUS_SUCCESS until the network mini-redirector changes this value on completion. If the call completed successfully, both of the members contain STATUS_SUCCESS. 

On failure to create a NET_ROOT structure, one of the following common error codes for the <b>NetRootStatus</b> member is returned (although other error codes are possible):

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CONNECTION_RESET</b></dt>
</dl>
</td>
<td width="60%">
The connection to the remote resource was reset. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_IO_TIMEOUT</b></dt>
</dl>
</td>
<td width="60%">
A time out occurred on an I/O request.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_RETRY</b></dt>
</dl>
</td>
<td width="60%">
A remote boot server was not ready to satisfy the request. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNEXPECTED_NETWORK_ERROR</b></dt>
</dl>
</td>
<td width="60%">
An unexpected network error occurred usually caused by an invalid handle.

</td>
</tr>
</table>
 

On failure to create a V_NET_ROOT structure, one of the following common error codes for the <i>VirtualNetRootStatus</i> is returned (although other error codes are possible):




## -remarks



The two important abstractions used in the interface between RDBSS and a network mini-redirector are the SRV_CALL structure and the NET_ROOT/V_NET_ROOT structure. An SRV_CALL structure corresponds to the context associated with a server with which a connection has been established. A NET_ROOT structure corresponds to a share on a server. A V_NET_ROOT structure could be viewed as a portion of the namespace below a NET_ROOT structure claimed by a network mini-redirector.

The creation of a NET_ROOT/V_NET_ROOT structure typically involves at least one network round trip. This operation can take considerable time to complete because a network connection with a remote resource may need to be established. To ensure that the asynchronous operations continue, the creation of a NET_ROOT/V_NET_ROOT structure is modeled as a two-phase activity. Each call to a network mini-redirector for creating a NET_ROOT/V_NET_ROOT structure is followed by a call back from the network mini-redirector to RDBSS that indicates to RDBSS the  completion status of the request to the network mini-redirector. Because RDBSS expects <i>MRxCreateVNetRoot</i> is completed asynchronously, RDBSS expects <i>MRxCreateVNetRoot</i> to return STATUS_PENDING. RDBSS will be notified using the callback routine when the call finally completes. 

<i>MRxCreateVNetRoot</i> must deal with two cases of interest:

<ol>
<li>
A new V_NET_ROOT structure and the associated new NET_ROOT structure are being created.

</li>
<li>
A new V_NET_ROOT structure that is associated with an existing NET_ROOT structure is being created.

</li>
</ol>
These two cases can be distinguished by checking if the context associated with a NET_ROOT structure is <b>NULL</b>. 

A network mini-redirector implementation of <i>MRxCreateVNetRoot</i> is expected to  return STATUS_PENDING to initial call. When processing is completed, the network mini-redirector would call the callback routine passed in as part of the <i>pCreateNetRootContext</i> parameter to notify RDBSS that the call was completed and return the completion status. The callback routine that the network mini-redirector should call up to is specified as the <b>Callback</b> member in the MRX_CREATENETROOT_CONTEXT structure passed as the <i>pCreateNetRootContext</i> parameter. The final completion status of the <i>MRxCreateVNetRoot</i> call must be stored in the <b>VirtualNetRootStatus</b> and <b>NetRootStatus</b> members of the <i>pCreateNetRootContext</i> parameter. Note that separate status is returned for the NET_ROOT and V_NET_ROOT structures.

The implementation of <i>MRxCreateVNetRoot</i> in a network mini-redirector is also complicated by the need for transport handles. Certain transport-related interfaces require a handle to be created and used for all communication. Creating a NET_ROOT or V_NET_ROOT structure may require establishing transport-related handles for network communications. Because the process of establishing a network connection can be time consuming, once a connection is established it makes sense to use the connection for communication as long as possible. Once a transport handle to a remote network resource is established, it can be reused by any number of other application requests. When a user application terminates, the handles associated with the process are deleted. For this reason, establishing transport handles in the context of a transient user-mode process that might be short-lived does not make sense. So a NET_ROOT or V_NET_ROOT structure normally needs to be initialized in the context of a well known process that will not disappear while these transport handles are being used for communication. 

One method used to manage this in network mini-redirectors is to have the RDBSS system process allocate these transport handles. This affects how the <i>MRxCreateVNetRoot</i> routine is executed. If the request to <i>MRxCreateVNetRoot</i> was issued in the context of the RDBSS system process, then this call can be executed immediately and does not need to be posted to a work queue. However, in order to avoid problems, if the request to <i>MRxCreateVNetRoot</i> is from any other process, the request would be posted to a system work queue using <a href="https://msdn.microsoft.com/library/windows/hardware/ff554398">RxDispatchToWorkerThread</a> for later execution. RDBSS will later use one of its system threads to process the work queue request and execute <i>MRxCreateVNetRoot</i>. This ensures that any transport handles will be owned by a system process. 

A network mini-redirector can determine if a call to <i>MRxCreateVNetRoot</i> was received directly from RDBSS by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff554481">RxGetRDBSSProcess</a>. <b>RxGetRDBSSProcess</b> returns the RDBBS process and this value can be compared with the current process returned by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549177">IoGetCurrentProcess</a>. If the call to <i>MRxCreateVNetRoot</i> was not initiated in the context of the RDBSS system process, then <i>MRxCreateVNetRoot</i> can return STATUS_PENDING and post the call to a work queue using <a href="https://msdn.microsoft.com/426d28fa-abfe-44d9-9b15-119f92367b40">RxDispatchToWorkerThread </a>for later execution by RDBSS. Normally, these calls would be posted to the <a href="https://msdn.microsoft.com/5bbebf1f-ca0f-44b7-a5cd-f06b637aa3de">DelayedWorkQueue</a>. 

It is up to the network mini-redirector to decide how <i>MRxCreateVNetRoot</i> is implemented. If this process can take a considerable amount of time, then this call should be completed asynchronously. If transport handles are needed, then the network mini-redirector may want a system process that is long-lived to establish these handles. 

In case the connection cannot be established, the network mini-redirector can try to transition the NET_ROOT and V_NET_ROOT structures into a disconnected mode (if this is supported) and establish the connection offline. 

When <i>MRxCreateVNetRoot</i> completes, the <i>pCreateNetRootContext</i> parameter should be modified with the appropriate NET_ROOT and V_NET_ROOT structure information that is updated from the network mini-redirector.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549177">IoGetCurrentProcess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549864">MRxCreateSrvCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550649">MRxExtractNetRootName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550653">MRxFinalizeNetRoot</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550656">MRxFinalizeSrvCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550663">MRxFinalizeVNetRoot</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550750">MRxPreparseName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550824">MRxSrvCallWinnerNotify</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554398">RxDispatchToWorkerThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554481">RxGetRDBSSProcess</a>
 

 

