---
UID: NC:mrx.PMRX_EXTENDFILE_CALLDOWN
title: PMRX_EXTENDFILE_CALLDOWN
author: windows-driver-content
description: The MRxExtendForCache routine is called by RDBSS to request that a network mini-redirector extend a file when the file is being cached by the cache manager.
old-location: ifsk\mrxextendforcache.htm
tech.root: ifsk
ms.assetid: 2fde7925-040b-4a8c-8a95-29321f1ae474
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: MRxExtendForCache, MRxExtendForCache routine [Installable File System Drivers], PMRX_EXTENDFILE_CALLDOWN, ifsk.mrxextendforcache, mrx/MRxExtendForCache, mrxref_9d9e2b3a-589c-41a3-b786-fbaaab97814a.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	mrx.h
api_name:
-	MRxExtendForCache
product:
- Windows
targetos: Windows
req.typenames: 
---

# PMRX_EXTENDFILE_CALLDOWN callback function


## -description


The<i> MRxExtendForCache</i> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector extend a file when the file is being cached by the cache manager. 


## -parameters




### -param RxContext [in, out]

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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549838">MRxAreFilesAliased</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549841">MRxCleanupFobx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549845">MRxCloseSrvOpen</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549847">MRxCollapseOpen</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549862">MRxCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549871">MRxDeallocateForFcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549872">MRxDeallocateForFobx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549879">MRxExtendForNonCache</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550669">MRxFlush</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550677">MRxForceClosed</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550691">MRxIsLockRealizable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550817">MRxShouldTryToCollapseThisOpen</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550839">MRxTruncate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550844">MRxZeroExtend</a>
 

 

