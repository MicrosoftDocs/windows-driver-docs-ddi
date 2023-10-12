---
UID: NC:mrx.PMRX_EXTENDFILE_CALLDOWN
title: PMRX_EXTENDFILE_CALLDOWN (mrx.h)
description: Learn more about the PMRX_EXTENDFILE_CALLDOWN callback function.
tech.root: ifsk
ms.date: 10/11/2023
keywords: ["PMRX_EXTENDFILE_CALLDOWN callback function"]
ms.keywords: MRxExtendForCache, MRxExtendForCache routine [Installable File System Drivers], PMRX_EXTENDFILE_CALLDOWN, ifsk.mrxextendforcache, mrx/MRxExtendForCache, mrxref_9d9e2b3a-589c-41a3-b786-fbaaab97814a.xml
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
 - PMRX_EXTENDFILE_CALLDOWN
 - mrx/PMRX_EXTENDFILE_CALLDOWN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - mrx.h
api_name:
 - PMRX_EXTENDFILE_CALLDOWN
---

# PMRX_EXTENDFILE_CALLDOWN callback function

## -description

The **MRxExtendForCache** routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that a network mini-redirector extend a file when the file is being cached by the cache manager.

## -parameters

### -param RxContext

[in, out] A pointer to the RX_CONTEXT structure. This parameter contains the IRP that is requesting the operation.

### -param NewFileSize

[in, out] A pointer to the LARGE_INTEGER structure indicating the byte count of the new file size.

### -param NewAllocationSize

[out] A pointer to the LARGE_INTEGER structure for storing the new allocation size when **MRxExtendForCache** returns.

## -returns

**MRxExtendForCache** returns STATUS_SUCCESS on success or an error code on failure.

## -remarks

**MRxExtendForCache** handles network requests to extend the file for cached I/O.

Before calling **MRxExtendForCache**, RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

* **LowIoContext.Operation** is set to LOWIO_OP_WRITE
* **LowIoContext.ParamsFor.ReadWrite.Flags** has the LOWIO_READWRITEFLAG_EXTENDING_FILESIZE bit set

A network mini-redirector that caches file or directory information may need to invalidate its cache information when the file is extended.

## -see-also

[**MRxAreFilesAliased**](nc-mrx-pmrx_chkfcb_calldown.md)

[**MRxCleanupFobx**](/previous-versions/windows/hardware/drivers/ff549841(v=vs.85))

[**MRxCloseSrvOpen**](nc-mrx-pmrx_calldown.md)

[**MRxCollapseOpen**](/windows-hardware/drivers/ifs/mrxcollapseopen)

[**MRxCreate**](/windows-hardware/drivers/ifs/mrxcreate)

[**MRxDeallocateForFcb**](nc-mrx-pmrx_deallocate_for_fcb.md)

[**MRxDeallocateForFobx**](nc-mrx-pmrx_deallocate_for_fobx.md)

[**MRxExtendForNonCache**](/windows-hardware/drivers/ifs/mrxextendfornoncache)

[**MRxFlush**](/windows-hardware/drivers/ifs/mrxflush)

[**MRxForceClosed**](nc-mrx-pmrx_forceclosed_calldown.md)

[**MRxIsLockRealizable**](nc-mrx-pmrx_is_lock_realizable.md)

[**MRxShouldTryToCollapseThisOpen**](/windows-hardware/drivers/ifs/mrxshouldtrytocollapsethisopen)

[**MRxTruncate**](/windows-hardware/drivers/ifs/mrxtruncate)

[**MRxZeroExtend**](/windows-hardware/drivers/ifs/mrxzeroextend)
