---
UID: NC:wdm.PCLFS_CLIENT_LFF_HANDLER_COMPLETE_CALLBACK
title: PCLFS_CLIENT_LFF_HANDLER_COMPLETE_CALLBACK (wdm.h)
description: The ClfsLogGrowthCompleteCallback function implements the actions that the client will take when space is freed in a log that had previously been full.
old-location: kernel\clfsloggrowthcompletecallback.htm
tech.root: kernel
ms.assetid: f8ebeaa9-e487-461b-8d95-50094bcc2bf5
ms.date: 04/30/2018
keywords: ["PCLFS_CLIENT_LFF_HANDLER_COMPLETE_CALLBACK callback function"]
ms.keywords: ClfsLogGrowthCompleteCallback, ClfsLogGrowthCompleteCallback callback function [Kernel-Mode Driver Architecture], Clfs_management_656d5a55-7a42-48c3-a788-d1eec6b5e11e.xml, PCLFS_CLIENT_LFF_HANDLER_COMPLETE_CALLBACK, PCLFS_CLIENT_LFF_HANDLER_COMPLETE_CALLBACK callback, kernel.clfsloggrowthcompletecallback, wdm/ClfsLogGrowthCompleteCallback
f1_keywords:
 - "wdm/ClfsLogGrowthCompleteCallback"
 - "ClfsLogGrowthCompleteCallback"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdm.h
api_name:
- ClfsLogGrowthCompleteCallback
targetos: Windows
req.typenames: 
---

# PCLFS_CLIENT_LFF_HANDLER_COMPLETE_CALLBACK callback function


## -description


The <i>ClfsLogGrowthCompleteCallback</i> function implements the actions that the client will take when space is freed in a log that had previously been full.


## -parameters




### -param LogFile 
[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">LOG_FILE_OBJECT</a> structure that represents the CLFS log stream whose log has finished growing.


### -param OperationStatus 
[in]
The status of the client's earlier request to handle a log file full condition. This will be either STATUS_SUCCESS or an error status that indicates the reason that the request could not be completed successfully.


### -param LogIsPinned 
[in]
If <b>TRUE</b>, specifies that the log tail is currently pinned;  <b>FALSE</b> if the log tail is not pinned.


### -param ClientData 
[in]
A pointer to client-supplied information.


## -remarks



Because a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsmgmthandlelogfilefull">ClfsMgmtHandleLogFileFull</a> completes asynchronously, any actions that the client will take when the log file full condition has been handled belong in the <i>ClfsLogGrowthCompleteCallback</i> function.

If a call to the <b>ClfsMgmtHandleLogFileFull</b> routine returned returns STATUS_PENDING, then the <i>ClfsLogGrowthCompleteCallback</i> function will be invoked when the operation completes. If a different status was returned, then the <i>ClfsLogGrowthCompleteCallback</i> function will not be invoked.

The <i>ClfsLogGrowthCompleteCallback</i> function should only perform a minimal amount of processing before returning. For example, the <i>ClfsLogGrowthCompleteCallback</i> function might follow the following procedure:

<ol>
<li>
If the value of the <i>OperationStatus</i> parameter is an error status, return.

</li>
<li>
If the value of the <i>OperationStatus</i> parameter is STATUS_SUCCESS, create and queue a work item to inform the client that it can resume processing.

</li>
</ol>
When a client uses the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsmgmtregistermanagedclient">ClfsMgmtRegisterManagedClient</a> routine to register with CLFS management, the client provides both a pointer to the <i>ClfsLogGrowthCompleteCallback</i> function and the custom data that will be passed as a parameter to the <i>ClfsLogGrowthCompleteCallback</i> function when this function is called.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsmgmthandlelogfilefull">ClfsMgmtHandleLogFileFull</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsmgmtregistermanagedclient">ClfsMgmtRegisterManagedClient</a>
 

 

