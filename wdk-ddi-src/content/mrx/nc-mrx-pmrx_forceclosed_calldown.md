---
UID: NC:mrx.PMRX_FORCECLOSED_CALLDOWN
title: PMRX_FORCECLOSED_CALLDOWN (mrx.h)
description: The MRxForceClosed routine is called by RDBSS to request that a network mini-redirector force a close. This routine is called when the condition of the SRV_OPEN structure is not good or the SRV_OPEN structure is marked as closed.
old-location: ifsk\mrxforceclosed.htm
tech.root: ifsk
ms.assetid: 81cbde46-e538-47dd-8b4a-e80dfb5e5b65
ms.date: 04/16/2018
keywords: ["PMRX_FORCECLOSED_CALLDOWN callback function"]
ms.keywords: MRxForceClosed, MRxForceClosed routine [Installable File System Drivers], PMRX_FORCECLOSED_CALLDOWN, ifsk.mrxforceclosed, mrx/MRxForceClosed, mrxref_4ebb7c98-0f0f-402e-b6f7-53e75c5cac54.xml
f1_keywords:
 - "mrx/MRxForceClosed"
 - "MRxForceClosed"
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
- MRxForceClosed
targetos: Windows
req.typenames: 
---

# PMRX_FORCECLOSED_CALLDOWN callback function


## -description


The<i> MRxForceClosed</i> routine is called by <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector force a close. This routine is called when the condition of the SRV_OPEN structure is not good or the SRV_OPEN structure is marked as closed.


## -parameters




### -param SrvOpen








#### - pSrvOpen [in]

A pointer to the SRV_OPEN structure. 


## -returns



<i>MRxForceClosed</i> returns STATUS_SUCCESS on success or an appropriate NTSTATUS value, such as the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
This routine is not implemented. 

</td>
</tr>
</table>
 




## -remarks



<i>MRxForceClosed</i> requests that the network mini-redirector force a close of a file system object.

<i>MRxForceClosed</i> is called by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizesrvopen">RxFinalizeSrvOpen</a> as part of the process to finalize an SRV_OPEN structure. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_chkfcb_calldown">MRxAreFilesAliased</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff549841(v=vs.85)">MRxCleanupFobx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_calldown">MRxCloseSrvOpen</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxcollapseopen">MRxCollapseOpen</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxcreate">MRxCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_deallocate_for_fcb">MRxDeallocateForFcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_deallocate_for_fobx">MRxDeallocateForFobx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_extendfile_calldown">MRxExtendForCache</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxextendfornoncache">MRxExtendForNonCache</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxflush">MRxFlush</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_is_lock_realizable">MRxIsLockRealizable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxshouldtrytocollapsethisopen">MRxShouldTryToCollapseThisOpen</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxtruncate">MRxTruncate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxzeroextend">MRxZeroExtend</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizesrvopen">RxFinalizeSrvOpen</a>
 

 

