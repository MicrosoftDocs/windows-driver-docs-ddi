---
UID: NC:wdm.PCLFS_CLIENT_ADVANCE_TAIL_CALLBACK
title: PCLFS_CLIENT_ADVANCE_TAIL_CALLBACK (wdm.h)
description: The ClfsAdvanceTailCallback function advances the base log sequence number (LSN) of the client's log.
old-location: kernel\clfsadvancetailcallback.htm
tech.root: kernel
ms.assetid: e5c3ac56-9e9f-40b8-b8a8-2eb4d41bca52
ms.date: 04/30/2018
keywords: ["PCLFS_CLIENT_ADVANCE_TAIL_CALLBACK callback function"]
ms.keywords: ClfsAdvanceTailCallback, ClfsAdvanceTailCallback callback function [Kernel-Mode Driver Architecture], Clfs_management_86e7d14f-866d-4023-9f97-d495ac16989f.xml, PCLFS_CLIENT_ADVANCE_TAIL_CALLBACK, PCLFS_CLIENT_ADVANCE_TAIL_CALLBACK callback, kernel.clfsadvancetailcallback, wdm/ClfsAdvanceTailCallback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
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
req.irql: Called at IRQL <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PCLFS_CLIENT_ADVANCE_TAIL_CALLBACK
 - wdm/PCLFS_CLIENT_ADVANCE_TAIL_CALLBACK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - ClfsAdvanceTailCallback
---

# PCLFS_CLIENT_ADVANCE_TAIL_CALLBACK callback function


## -description

The <i>ClfsAdvanceTailCallback</i> function advances the base log sequence number (LSN) of the client's log.

## -parameters

### -param LogFile 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">LOG_FILE_OBJECT</a> structure that represents the CLFS log stream whose tail should be advanced.

### -param TargetLsn 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_cls_lsn">CLFS_LSN</a> structure that contains the LSN that the client should advance its tail to or beyond.

### -param ClientData 

[in]
A pointer to client-supplied information. You specify this data in the <b>AdvanceTailCallbackData</b> member of the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_clfs_mgmt_client_registration">CLFS_MGMT_CLIENT_REGISTRATION</a> structure.

## -returns

The <i>ClfsAdvanceTailCallback</i> function should return either STATUS_PENDING or an error status. A return value of STATUS_PENDING indicates that the request to move the client's log tail will be completed asynchronously. The <b>ClfsMgmtAdvanceTailCallback</b> function must not return STATUS_SUCCESS, even if it completes synchronously.

## -remarks

The <i>ClfsAdvanceTailCallback</i> function is called when CLFS management requests that the client advance its log tail.

The <i>ClfsAdvanceTailCallback</i> function must only perform a minimal amount of processing before returning. For example, the <i>ClfsAdvanceTailCallback</i> function might follow this procedure:

<ol>
<li>
If the request cannot be processed, return an error status.

</li>
<li>
If the request can be processed, create and queue a work item to perform the actions that are required to move the client's tail, and then return STATUS_PENDING. For more information on queuing a worker thread, see <a href="/windows-hardware/drivers/kernel/system-worker-threads">System Worker Threads</a>.

</li>
</ol>
When a client calls the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsmgmtregistermanagedclient">ClfsMgmtRegisterManagedClient</a> routine to register with CLFS management, the client provides both a pointer to the <i>ClfsAdvanceTailCallback</i> function and the custom data that will be passed as a parameter to the <i>ClfsAdvanceTailCallback</i> function when this function is called.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_clfs_mgmt_client_registration">CLFS_MGMT_CLIENT_REGISTRATION</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsadvancelogbase">ClfsAdvanceLogBase</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsmgmtregistermanagedclient">ClfsMgmtRegisterManagedClient</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsmgmttailadvancefailure">ClfsMgmtTailAdvanceFailure</a>