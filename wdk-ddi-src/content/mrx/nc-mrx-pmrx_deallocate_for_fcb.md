---
UID: NC:mrx.PMRX_DEALLOCATE_FOR_FCB
title: PMRX_DEALLOCATE_FOR_FCB (mrx.h)
description: Learn more about the PMRX_DEALLOCATE_FOR_FCB callback function.
tech.root: ifsk
ms.date: 10/11/2023
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
 - PMRX_DEALLOCATE_FOR_FCB
---

# PMRX_DEALLOCATE_FOR_FCB callback function

## -description

The **MRxDeallocateForFcb** routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that the network mini-redirector deallocate an FCB structure. This call is in response to a request to close a file system object.

## -parameters

### -param Fcb

[in, out] A pointer to the FCB structure to deallocate.

## -returns

**MRxDeallocateForFcb** returns STATUS_SUCCESS.

## -remarks

**MRxDeallocateForFcb** is called by [**RxFinalizeNetFCB**](../rxprocs/nf-rxprocs-rxfinalizenetfcb.md) as part of the process to finalize an FCB structure. The calls to **RxFinalizeNetFCB** and **MRxDeallocateForFcb** occur when an [**IRP_MJ_CLOSE**](/windows-hardware/drivers/kernel/irp-mj-close) request is received.

## -see-also

[**MRxAreFilesAliased**](nc-mrx-pmrx_chkfcb_calldown.md)

[**MRxCleanupFobx**](/previous-versions/windows/hardware/drivers/ff549841(v=vs.85))

[**MRxCloseSrvOpen**](nc-mrx-pmrx_calldown.md)

[**MRxCollapseOpen**](/windows-hardware/drivers/ifs/mrxcollapseopen)

[**MRxCreate**](/windows-hardware/drivers/ifs/mrxcreate)

[**MRxDeallocateForFobx**](nc-mrx-pmrx_deallocate_for_fobx.md)

[**MRxExtendForCache**](nc-mrx-pmrx_extendfile_calldown.md)

[**MRxExtendForNonCache**](/windows-hardware/drivers/ifs/mrxextendfornoncache)

[**MRxFlush**](/windows-hardware/drivers/ifs/mrxflush)

[**MRxForceClosed**](nc-mrx-pmrx_forceclosed_calldown.md)

[**MRxIsLockRealizable**](nc-mrx-pmrx_is_lock_realizable.md)

[**MRxShouldTryToCollapseThisOpen**](/windows-hardware/drivers/ifs/mrxshouldtrytocollapsethisopen)

[**MRxTruncate**](/windows-hardware/drivers/ifs/mrxtruncate)

[**MRxZeroExtend**](/windows-hardware/drivers/ifs/mrxzeroextend)

[**RxFinalizeNetFCB**](../rxprocs/nf-rxprocs-rxfinalizenetfcb.md)
