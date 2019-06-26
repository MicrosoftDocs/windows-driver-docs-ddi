---
UID: NC:mrx.PMRX_IS_LOCK_REALIZABLE
title: PMRX_IS_LOCK_REALIZABLE (mrx.h)
description: The MRxIsLockRealizable routine is called by RDBSS to request that a network mini-redirector indicate whether a specific byte-range lock is supported on this NET_ROOT structure.
old-location: ifsk\mrxislockrealizable.htm
tech.root: ifsk
ms.assetid: 4b8c9a94-a81e-4a02-b68c-10b2fb64157f
ms.date: 04/16/2018
ms.keywords: MRxIsLockRealizable, MRxIsLockRealizable routine [Installable File System Drivers], PMRX_IS_LOCK_REALIZABLE, ifsk.mrxislockrealizable, mrx/MRxIsLockRealizable, mrxref_52518201-df6f-40ab-803d-14d8fc0993f6.xml
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- mrx.h
api_name:
- MRxIsLockRealizable
product:
- Windows
targetos: Windows
req.typenames: 
---

# PMRX_IS_LOCK_REALIZABLE callback function


## -description


The<i> MRxIsLockRealizable</i> routine is called by <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector indicate whether a specific byte-range lock is supported on this NET_ROOT structure.


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
The byte range lock that is requested is not supported. A network mini-redirector would return this value for a lock request that is not supported even if other types of byte range locks are supported. Unsupported locks might include 64-bit locks (the <b>ByteOffset->HighPart</b> member is nonzero), zero-length locks (the <b>Length</b> parameter is zero), or shared locks (the LOWIO_LOCKSFLAG_EXCLUSIVELOCK bit of the <i>LowIoLockFlags</i> parameter is not set). 

</td>
</tr>
</table>
 




## -remarks



<i>MRxIsLockRealizable</i> determines whether the specific byte-range lock requested is supported on this NET_ROOT structure. A network mini-redirector might support certain byte range locks and not support others. For example, a network mini-redirector might only support 32-bit byte range locks or exclusive locks.

<i>MRxIsLockRealizable</i> is called in response to receiving an IRP with the IRP_MN_LOCK minor function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/mrx/nc-mrx-pmrx_chkfcb_calldown">MRxAreFilesAliased</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff549841(v=vs.85)">MRxCleanupFobx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/mrx/nc-mrx-pmrx_calldown">MRxCloseSrvOpen</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxcollapseopen">MRxCollapseOpen</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxcreate">MRxCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/mrx/nc-mrx-pmrx_deallocate_for_fcb">MRxDeallocateForFcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/mrx/nc-mrx-pmrx_deallocate_for_fobx">MRxDeallocateForFobx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/mrx/nc-mrx-pmrx_extendfile_calldown">MRxExtendForCache</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxextendfornoncache">MRxExtendForNonCache</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxflush">MRxFlush</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/mrx/nc-mrx-pmrx_forceclosed_calldown">MRxForceClosed</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxshouldtrytocollapsethisopen">MRxShouldTryToCollapseThisOpen</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxtruncate">MRxTruncate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxzeroextend">MRxZeroExtend</a>
 

 

