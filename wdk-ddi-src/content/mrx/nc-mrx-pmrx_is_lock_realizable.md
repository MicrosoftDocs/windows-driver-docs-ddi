---
UID: NC:mrx.PMRX_IS_LOCK_REALIZABLE
title: PMRX_IS_LOCK_REALIZABLE
author: windows-driver-content
description: The MRxIsLockRealizable routine is called by RDBSS to request that a network mini-redirector indicate whether a specific byte-range lock is supported on this NET_ROOT structure.
old-location: ifsk\mrxislockrealizable.htm
old-project: ifsk
ms.assetid: 4b8c9a94-a81e-4a02-b68c-10b2fb64157f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ifsk.mrxislockrealizable, MRxIsLockRealizable, MRxIsLockRealizable routine [Installable File System Drivers], MRxIsLockRealizable, PMRX_IS_LOCK_REALIZABLE, PMRX_IS_LOCK_REALIZABLE, mrx/MRxIsLockRealizable, mrxref_52518201-df6f-40ab-803d-14d8fc0993f6.xml
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
-	MRxIsLockRealizable
product: Windows
targetos: Windows
req.typenames: SetDSMCounters_IN, *PSetDSMCounters_IN
---

# PMRX_IS_LOCK_REALIZABLE callback


## -description


The<i> MRxIsLockRealizable</i> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector indicate whether a specific byte-range lock is supported on this NET_ROOT structure.


## -prototype


````
PMRX_IS_LOCK_REALIZABLE MRxIsLockRealizable;

NTSTATUS MRxIsLockRealizable(
  _Inout_ PMRX_FCB       pFcb,
  _In_    PLARGE_INTEGER ByteOffset,
  _In_    PLARGE_INTEGER Length,
  _In_    ULONG          LowIoLockFlags
)
{ ... }
````


## -parameters




### -param Fcb


### -param ByteOffset [in]

A value indicating the byte offset for the byte range lock. 


### -param Length [in]

A value indicating the length for the byte range lock. 


### -param LowIoLockFlags [in]

A value indicating the I/O lock flags. This parameter is a bitmask that contains any combination of the following values: 


#### - pFcb [in, out]

A pointer to the FCB structure. 


## -returns



<i>MRxIsLockRealizable</i> returns STATUS_SUCCESS on success or an appropriate NTSTATUS value, such as the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The byte range lock that is requested is not supported. A network mini-redirector would return this value for a lock request that is not supported even if other types of byte range locks are supported. Unsupported locks might include 64-bit locks (the <b>ByteOffset-&gt;HighPart</b> member is nonzero), zero-length locks (the <b>Length</b> parameter is zero), or shared locks (the LOWIO_LOCKSFLAG_EXCLUSIVELOCK bit of the <i>LowIoLockFlags</i> parameter is not set). 

</td>
</tr>
</table>
 




## -remarks



<i>MRxIsLockRealizable</i> determines whether the specific byte-range lock requested is supported on this NET_ROOT structure. A network mini-redirector might support certain byte range locks and not support others. For example, a network mini-redirector might only support 32-bit byte range locks or exclusive locks.

<i>MRxIsLockRealizable</i> is called in response to receiving an IRP with the IRP_MN_LOCK minor function.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550669">MRxFlush</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549841">MRxCleanupFobx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549862">MRxCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550844">MRxZeroExtend</a>



<a href="..\mrx\nc-mrx-pmrx_forceclosed_calldown.md">MRxForceClosed</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549847">MRxCollapseOpen</a>



<a href="..\mrx\nc-mrx-pmrx_deallocate_for_fobx.md">MRxDeallocateForFobx</a>



<a href="..\mrx\nc-mrx-pmrx_calldown.md">MRxCloseSrvOpen</a>



<a href="..\mrx\nc-mrx-pmrx_extendfile_calldown.md">MRxExtendForCache</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550817">MRxShouldTryToCollapseThisOpen</a>



<a href="..\mrx\nc-mrx-pmrx_deallocate_for_fcb.md">MRxDeallocateForFcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550839">MRxTruncate</a>



<a href="..\mrx\nc-mrx-pmrx_chkfcb_calldown.md">MRxAreFilesAliased</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549879">MRxExtendForNonCache</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PMRX_IS_LOCK_REALIZABLE routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

