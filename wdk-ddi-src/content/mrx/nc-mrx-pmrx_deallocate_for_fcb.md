---
UID: NC:mrx.PMRX_DEALLOCATE_FOR_FCB
title: PMRX_DEALLOCATE_FOR_FCB (mrx.h)
description: The MRxDeallocateForFcb routine is called by RDBSS to request that the network mini-redirector deallocate an FCB structure. This call is in response to a request to close a file system object.
old-location: ifsk\mrxdeallocateforfcb.htm
tech.root: ifsk
ms.assetid: 4347f481-cd8f-4a88-92e0-f6bc7a4b7ffb
ms.date: 04/16/2018
keywords: ["PMRX_DEALLOCATE_FOR_FCB callback function"]
ms.keywords: MRxDeallocateForFcb, MRxDeallocateForFcb routine [Installable File System Drivers], PMRX_DEALLOCATE_FOR_FCB, ifsk.mrxdeallocateforfcb, mrx/MRxDeallocateForFcb, mrxref_02a9e4a3-db00-48e1-ac2e-cd6a47ae4c37.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PMRX_DEALLOCATE_FOR_FCB
 - mrx/PMRX_DEALLOCATE_FOR_FCB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - mrx.h
api_name:
 - MRxDeallocateForFcb
---

# PMRX_DEALLOCATE_FOR_FCB callback function


## -description

The<i> MRxDeallocateForFcb</i> routine is called by <a href="/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that the network mini-redirector deallocate an FCB structure. This call is in response to a request to close a file system object.

## -parameters

### -param Fcb

#### - pFcb [in, out]

A pointer to the FCB structure to deallocate.

## -returns

<i>MRxDeallocateForFcb</i> returns STATUS_SUCCESS.

## -remarks

<i>MRxDeallocateForFcb</i> is called by <a href="/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxfinalizenetfcb">RxFinalizeNetFCB</a> as part of the process to finalize an FCB structure. The calls to <b>RxFinalizeNetFCB</b> and <i>MRxDeallocateForFcb</i> occur when an <a href="/windows-hardware/drivers/kernel/irp-mj-close">IRP_MJ_CLOSE</a> request is received.

## -see-also

<a href="/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_chkfcb_calldown">MRxAreFilesAliased</a>



<a href="/previous-versions/windows/hardware/drivers/ff549841(v=vs.85)">MRxCleanupFobx</a>



<a href="/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_calldown">MRxCloseSrvOpen</a>



<a href="/windows-hardware/drivers/ifs/mrxcollapseopen">MRxCollapseOpen</a>



<a href="/windows-hardware/drivers/ifs/mrxcreate">MRxCreate</a>



<a href="/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_deallocate_for_fobx">MRxDeallocateForFobx</a>



<a href="/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_extendfile_calldown">MRxExtendForCache</a>



<a href="/windows-hardware/drivers/ifs/mrxextendfornoncache">MRxExtendForNonCache</a>



<a href="/windows-hardware/drivers/ifs/mrxflush">MRxFlush</a>



<a href="/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_forceclosed_calldown">MRxForceClosed</a>



<a href="/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_is_lock_realizable">MRxIsLockRealizable</a>



<a href="/windows-hardware/drivers/ifs/mrxshouldtrytocollapsethisopen">MRxShouldTryToCollapseThisOpen</a>



<a href="/windows-hardware/drivers/ifs/mrxtruncate">MRxTruncate</a>



<a href="/windows-hardware/drivers/ifs/mrxzeroextend">MRxZeroExtend</a>



<a href="/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxfinalizenetfcb">RxFinalizeNetFCB</a>