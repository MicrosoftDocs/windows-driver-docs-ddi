---
UID: NC:mrx.PMRX_DEALLOCATE_FOR_FOBX
title: PMRX_DEALLOCATE_FOR_FOBX (mrx.h)
description: Learn more about the PMRX_DEALLOCATE_FOR_FOBX callback function.
tech.root: ifsk
ms.date: 10/11/2023
keywords: ["PMRX_DEALLOCATE_FOR_FOBX callback function"]
ms.keywords: MRxDeallocateForFobx, MRxDeallocateForFobx routine [Installable File System Drivers], PMRX_DEALLOCATE_FOR_FOBX, ifsk.mrxdeallocateforfobx, mrx/MRxDeallocateForFobx, mrxref_2b2fa1f1-19f9-4a9b-9105-7c5946428b88.xml
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
 - PMRX_DEALLOCATE_FOR_FOBX
 - mrx/PMRX_DEALLOCATE_FOR_FOBX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - mrx.h
api_name:
 - PMRX_DEALLOCATE_FOR_FOBX
---

# PMRX_DEALLOCATE_FOR_FOBX callback function

## -description

The **MRxDeallocateForFobx** routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that the network mini-redirector deallocate an FOBX structure. This call is in response to a request to close a file system object.

## -parameters

### -param Fobx

[in, out] A pointer to the FOBX structure to deallocate.

## -returns

**MRxDeallocateForFobx** returns STATUS_SUCCESS.

## -remarks

**MRxDeallocateForFobx** is called by [**RxFinalizeNetFOBX**](../fcb/nf-fcb-rxfinalizenetfobx.md) as part of the process to finalize an FOBX structure. The calls to **RxFinalizeNetFOBX** and **MRxDeallocateForFobx** occurs when an [**IRP_MJ_CLOSE**](/windows-hardware/drivers/kernel/irp-mj-close) request is received.

RDBSS ignores the return value from **MRxDeallocateForFobx**.

## -see-also

[**MRxAreFilesAliased**](nc-mrx-pmrx_chkfcb_calldown.md)

[**MRxCleanupFobx**](/previous-versions/windows/hardware/drivers/ff549841(v=vs.85))

[**MRxCloseSrvOpen**](nc-mrx-pmrx_calldown.md)

[**MRxCollapseOpen**](/windows-hardware/drivers/ifs/mrxcollapseopen)

[**MRxCreate**](/windows-hardware/drivers/ifs/mrxcreate)

[**MRxDeallocateForFcb**](nc-mrx-pmrx_deallocate_for_fcb.md)

[**MRxExtendForCache**](nc-mrx-pmrx_extendfile_calldown.md)

[**MRxExtendForNonCache**](/windows-hardware/drivers/ifs/mrxextendfornoncache)

[**MRxFlush**](/windows-hardware/drivers/ifs/mrxflush)

[**MRxForceClosed**](nc-mrx-pmrx_forceclosed_calldown.md)

[**MRxIsLockRealizable**](nc-mrx-pmrx_is_lock_realizable.md)

[**MRxShouldTryToCollapseThisOpen**](/windows-hardware/drivers/ifs/mrxshouldtrytocollapsethisopen)

[**MRxTruncate**](/windows-hardware/drivers/ifs/mrxtruncate)

[**MRxZeroExtend**](/windows-hardware/drivers/ifs/mrxzeroextend)

[**RxFinalizeNetFOBX**](../fcb/nf-fcb-rxfinalizenetfobx.md)

[**RxFinalizeNetFCB**](../rxprocs/nf-rxprocs-rxfinalizenetfcb.md)
