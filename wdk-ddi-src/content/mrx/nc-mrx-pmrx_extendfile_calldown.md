---
UID: NC:mrx.PMRX_EXTENDFILE_CALLDOWN
title: PMRX_EXTENDFILE_CALLDOWN (mrx.h)
description: The MRxExtendForCache routine is called by RDBSS to request that a network mini-redirector extend a file when the file is being cached by the cache manager.
old-location: ifsk\mrxextendforcache.htm
tech.root: ifsk
ms.date: 04/16/2018
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
 - MRxExtendForCache
---

# PMRX_EXTENDFILE_CALLDOWN callback function


## -description

The<i> MRxExtendForCache</i> routine is called by <a href="/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector extend a file when the file is being cached by the cache manager.

## -parameters

### -param RxContext 

[in, out]
A pointer to the RX_CONTEXT structure. This parameter contains the IRP that is requesting the operation.

### -param NewFileSize

### -param NewAllocationSize

#### - pNewAllocationSize [out]

A pointer to the LARGE_INTEGER structure for storing the new allocation size when <i>MRxExtendForCache</i> returns. 


#### - pNewFileSize [in, out]

A pointer to the LARGE_INTEGER structure indicating the byte count of the new file size.

## -returns

<i>MRxExtendForCache</i> returns STATUS_SUCCESS on success or an error code on failure.

## -remarks

<i>MRxExtendForCache</i> handles network requests to extend the file for cached I/O.

Before calling<i> MRxExtendForCache</i>, RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:

<b>LowIoContext.Operation </b>is set to LOWIO_OP_WRITE

<b>LowIoContext.ParamsFor.ReadWrite.Flags</b> has the LOWIO_READWRITEFLAG_EXTENDING_FILESIZE bit set

A network mini-redirector that caches file or directory information may need to invalidate its cache information when the file is extended.

## -see-also

<a href="/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_chkfcb_calldown">MRxAreFilesAliased</a>



<a href="/previous-versions/windows/hardware/drivers/ff549841(v=vs.85)">MRxCleanupFobx</a>



<a href="/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_calldown">MRxCloseSrvOpen</a>



<a href="/windows-hardware/drivers/ifs/mrxcollapseopen">MRxCollapseOpen</a>



<a href="/windows-hardware/drivers/ifs/mrxcreate">MRxCreate</a>



<a href="/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_deallocate_for_fcb">MRxDeallocateForFcb</a>



<a href="/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_deallocate_for_fobx">MRxDeallocateForFobx</a>



<a href="/windows-hardware/drivers/ifs/mrxextendfornoncache">MRxExtendForNonCache</a>



<a href="/windows-hardware/drivers/ifs/mrxflush">MRxFlush</a>



<a href="/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_forceclosed_calldown">MRxForceClosed</a>



<a href="/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_is_lock_realizable">MRxIsLockRealizable</a>



<a href="/windows-hardware/drivers/ifs/mrxshouldtrytocollapsethisopen">MRxShouldTryToCollapseThisOpen</a>



<a href="/windows-hardware/drivers/ifs/mrxtruncate">MRxTruncate</a>



<a href="/windows-hardware/drivers/ifs/mrxzeroextend">MRxZeroExtend</a>
