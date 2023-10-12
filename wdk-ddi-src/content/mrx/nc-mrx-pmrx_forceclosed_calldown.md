---
UID: NC:mrx.PMRX_FORCECLOSED_CALLDOWN
title: PMRX_FORCECLOSED_CALLDOWN (mrx.h)
description: Learn more about the PMRX_FORCECLOSED_CALLDOWN callback function.
tech.root: ifsk
ms.date: 10/11/2023
keywords: ["PMRX_FORCECLOSED_CALLDOWN callback function"]
ms.keywords: MRxForceClosed, MRxForceClosed routine [Installable File System Drivers], PMRX_FORCECLOSED_CALLDOWN, ifsk.mrxforceclosed, mrx/MRxForceClosed, mrxref_4ebb7c98-0f0f-402e-b6f7-53e75c5cac54.xml
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
 - PMRX_FORCECLOSED_CALLDOWN
 - mrx/PMRX_FORCECLOSED_CALLDOWN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - mrx.h
api_name:
 - PMRX_FORCECLOSED_CALLDOWN
---

# PMRX_FORCECLOSED_CALLDOWN callback function

## -description

The **MRxForceClosed** routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that a network mini-redirector force a close. This routine is called when the condition of the SRV_OPEN structure is not good or the SRV_OPEN structure is marked as closed.

## -parameters

### -param SrvOpen

[in] A pointer to the SRV_OPEN structure.

## -returns

**MRxForceClosed** returns STATUS_SUCCESS on success or an appropriate NTSTATUS value, such as the following:

| Return code | Description |
| ------------- | ------------- |
| STATUS_NOT_IMPLEMENTED | This routine is not implemented.

## -remarks

**MRxForceClosed** requests that the network mini-redirector force a close of a file system object.

**MRxForceClosed** is called by [**RxFinalizeSrvOpen**](../fcb/nf-fcb-rxfinalizesrvopen.md) as part of the process to finalize an SRV_OPEN structure.

## -see-also

[**MRxAreFilesAliased**](nc-mrx-pmrx_chkfcb_calldown.md)

[**MRxCleanupFobx**](/previous-versions/windows/hardware/drivers/ff549841(v=vs.85))

[**MRxCloseSrvOpen**](nc-mrx-pmrx_calldown.md)

[**MRxCollapseOpen**](/windows-hardware/drivers/ifs/mrxcollapseopen)

[**MRxCreate**](/windows-hardware/drivers/ifs/mrxcreate)

[**MRxDeallocateForFbc**](nc-mrx-pmrx_deallocate_for_fbc.md)

[**MRxDeallocateForFobx**](nc-mrx-pmrx_deallocate_for_fobx.md)

[**MRxExtendForCache**](nc-mrx-pmrx_extendfile_calldown.md)

[**MRxExtendForNonCache**](/windows-hardware/drivers/ifs/mrxextendfornoncache)

[**MRxFlush**](/windows-hardware/drivers/ifs/mrxflush)

[**MRxIsLockRealizable**](nc-mrx-pmrx_is_lock_realizable.md)

[**MRxShouldTryToCollapseThisOpen**](/windows-hardware/drivers/ifs/mrxshouldtrytocollapsethisopen)

[**MRxTruncate**](/windows-hardware/drivers/ifs/mrxtruncate)

[**MRxZeroExtend**](/windows-hardware/drivers/ifs/mrxzeroextend)

[**RxFinalizeSrvOpen**](../fcb/nf-fcb-rxfinalizesrvopen.md)
