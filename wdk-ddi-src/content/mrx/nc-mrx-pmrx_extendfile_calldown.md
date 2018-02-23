---
UID: NC:mrx.PMRX_EXTENDFILE_CALLDOWN
title: PMRX_EXTENDFILE_CALLDOWN
author: windows-driver-content
description: The MRxExtendForCache routine is called by RDBSS to request that a network mini-redirector extend a file when the file is being cached by the cache manager.
old-location: ifsk\mrxextendforcache.htm
old-project: ifsk
ms.assetid: 2fde7925-040b-4a8c-8a95-29321f1ae474
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ifsk.mrxextendforcache, MRxExtendForCache, MRxExtendForCache routine [Installable File System Drivers], MRxExtendForCache, PMRX_EXTENDFILE_CALLDOWN, PMRX_EXTENDFILE_CALLDOWN, mrx/MRxExtendForCache, mrxref_9d9e2b3a-589c-41a3-b786-fbaaab97814a.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	mrx.h
apiname:
-	MRxExtendForCache
product: Windows
targetos: Windows
req.typenames: SetDSMCounters_IN, *PSetDSMCounters_IN
---

# PMRX_EXTENDFILE_CALLDOWN callback


## -description


The<i> MRxExtendForCache</i> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector extend a file when the file is being cached by the cache manager. 


## -prototype


````
PMRX_EXTENDFILE_CALLDOWN MRxExtendForCache;

ULONG MRxExtendForCache(
  _Inout_ PRX_CONTEXT    RxContext,
  _Inout_ PLARGE_INTEGER pNewFileSize,
  _Out_   PLARGE_INTEGER pNewAllocationSize
)
{ ... }
````


## -parameters




### -param RxContext [in, out]

A pointer to the RX_CONTEXT structure. This parameter contains the IRP that is requesting the operation. 


### -param NewFileSize


### -param NewAllocationSize








#### - pNewFileSize [in, out]

A pointer to the LARGE_INTEGER structure indicating the byte count of the new file size. 


#### - pNewAllocationSize [out]

A pointer to the LARGE_INTEGER structure for storing the new allocation size when <i>MRxExtendForCache</i> returns. 


## -returns



<i>MRxExtendForCache</i> returns STATUS_SUCCESS on success or an error code on failure. 




## -remarks



<i>MRxExtendForCache</i> handles network requests to extend the file for cached I/O.

Before calling<i> MRxExtendForCache</i>, RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:

<b>LowIoContext.Operation </b>is set to LOWIO_OP_WRITE

<b>LowIoContext.ParamsFor.ReadWrite.Flags</b> has the LOWIO_READWRITEFLAG_EXTENDING_FILESIZE bit set

A network mini-redirector that caches file or directory information may need to invalidate its cache information when the file is extended.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550669">MRxFlush</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549841">MRxCleanupFobx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549862">MRxCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550844">MRxZeroExtend</a>



<a href="..\mrx\nc-mrx-pmrx_forceclosed_calldown.md">MRxForceClosed</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549847">MRxCollapseOpen</a>



<a href="..\mrx\nc-mrx-pmrx_deallocate_for_fobx.md">MRxDeallocateForFobx</a>



<a href="..\mrx\nc-mrx-pmrx_calldown.md">MRxCloseSrvOpen</a>



<a href="..\mrx\nc-mrx-pmrx_is_lock_realizable.md">MRxIsLockRealizable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550817">MRxShouldTryToCollapseThisOpen</a>



<a href="..\mrx\nc-mrx-pmrx_deallocate_for_fcb.md">MRxDeallocateForFcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550839">MRxTruncate</a>



<a href="..\mrx\nc-mrx-pmrx_chkfcb_calldown.md">MRxAreFilesAliased</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549879">MRxExtendForNonCache</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PMRX_EXTENDFILE_CALLDOWN routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

