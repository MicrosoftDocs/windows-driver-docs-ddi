---
UID: NC:mrx.PMRX_DEALLOCATE_FOR_FOBX
title: PMRX_DEALLOCATE_FOR_FOBX (mrx.h)
description: The MRxDeallocateForFobx routine is called by RDBSS to request that the network mini-redirector deallocate an FOBX structure. This call is in response to a request to close a file system object.
old-location: ifsk\mrxdeallocateforfobx.htm
tech.root: ifsk
ms.assetid: 3b33df22-7757-4270-8cb0-59e8f5d5a80a
ms.date: 04/16/2018
keywords: ["PMRX_DEALLOCATE_FOR_FOBX callback function"]
ms.keywords: MRxDeallocateForFobx, MRxDeallocateForFobx routine [Installable File System Drivers], PMRX_DEALLOCATE_FOR_FOBX, ifsk.mrxdeallocateforfobx, mrx/MRxDeallocateForFobx, mrxref_2b2fa1f1-19f9-4a9b-9105-7c5946428b88.xml
f1_keywords:
 - "mrx/MRxDeallocateForFobx"
 - "MRxDeallocateForFobx"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- mrx.h
api_name:
- MRxDeallocateForFobx
targetos: Windows
req.typenames: 
---

# PMRX_DEALLOCATE_FOR_FOBX callback function


## -description


The<i> MRxDeallocateForFobx</i> routine is called by <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that the network mini-redirector deallocate an FOBX structure. This call is in response to a request to close a file system object.


## -parameters




### -param Fobx








#### - pFobx [in, out]

A pointer to the FOBX structure to deallocate.


## -returns



<i>MRxDeallocateForFobx</i> returns STATUS_SUCCESS.




## -remarks



<i>MRxDeallocateForFobx</i> is called by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizenetfobx">RxFinalizeNetFOBX</a> as part of the process to finalize an FOBX structure. The calls to <b>RxFinalizeNetFOBX</b> and <i>MRxDeallocateForFobx</i> occurs when an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-close">IRP_MJ_CLOSE</a> request is received.

RDBSS ignores the return value from <i>MRxDeallocateForFobx</i>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_chkfcb_calldown">MRxAreFilesAliased</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff549841(v=vs.85)">MRxCleanupFobx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_calldown">MRxCloseSrvOpen</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxcollapseopen">MRxCollapseOpen</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxcreate">MRxCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_deallocate_for_fcb">MRxDeallocateForFcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_deallocate_for_fobx">MRxDeallocateForFobx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_extendfile_calldown">MRxExtendForCache</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxextendfornoncache">MRxExtendForNonCache</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxflush">MRxFlush</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_forceclosed_calldown">MRxForceClosed</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_is_lock_realizable">MRxIsLockRealizable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxshouldtrytocollapsethisopen">MRxShouldTryToCollapseThisOpen</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxtruncate">MRxTruncate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxzeroextend">MRxZeroExtend</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizenetfobx">RxFinalizeNetFOBX</a>
 

 

