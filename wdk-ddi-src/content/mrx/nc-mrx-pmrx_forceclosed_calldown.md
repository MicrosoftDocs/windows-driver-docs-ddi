---
UID: NC:mrx.PMRX_FORCECLOSED_CALLDOWN
title: PMRX_FORCECLOSED_CALLDOWN
author: windows-driver-content
description: The MRxForceClosed routine is called by RDBSS to request that a network mini-redirector force a close. This routine is called when the condition of the SRV_OPEN structure is not good or the SRV_OPEN structure is marked as closed.
old-location: ifsk\mrxforceclosed.htm
old-project: ifsk
ms.assetid: 81cbde46-e538-47dd-8b4a-e80dfb5e5b65
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _SetDSMCounters_IN, SetDSMCounters_IN, *PSetDSMCounters_IN
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
req.alt-api: MRxForceClosed
req.alt-loc: mrx.h
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
req.typenames: SetDSMCounters_IN, *PSetDSMCounters_IN
---

# PMRX_FORCECLOSED_CALLDOWN callback



## -description
The<i> MRxForceClosed</i> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector force a close. This routine is called when the condition of the SRV_OPEN structure is not good or the SRV_OPEN structure is marked as closed.



## -prototype

````
PMRX_FORCECLOSED_CALLDOWN MRxForceClosed;

NTSTATUS MRxForceClosed(
  _In_ PMRX_SRV_OPEN pSrvOpen
)
{ ... }
````


## -parameters

### -param pSrvOpen [in]

A pointer to the SRV_OPEN structure. 


## -returns
<i>MRxForceClosed</i> returns STATUS_SUCCESS on success or an appropriate NTSTATUS value, such as the following: 
<dl>
<dt><b>STATUS_NOT_IMPLEMENTED</b></dt>
</dl>This routine is not implemented. 

 


## -remarks
<i>MRxForceClosed</i> requests that the network mini-redirector force a close of a file system object.

<i>MRxForceClosed</i> is called by <a href="..\fcb\nf-fcb-rxfinalizesrvopen.md">RxFinalizeSrvOpen</a> as part of the process to finalize an SRV_OPEN structure. 


## -see-also
<dl>
<dt>
<a href="..\mrx\nc-mrx-pmrx_chkfcb_calldown.md">MRxAreFilesAliased</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549841">MRxCleanupFobx</a>
</dt>
<dt>
<a href="..\mrx\nc-mrx-pmrx_calldown.md">MRxCloseSrvOpen</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549847">MRxCollapseOpen</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549862">MRxCreate</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549871">MRxDeallocateForFcb</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549872">MRxDeallocateForFobx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549878">MRxExtendForCache</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549879">MRxExtendForNonCache</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550669">MRxFlush</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550691">MRxIsLockRealizable</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550817">MRxShouldTryToCollapseThisOpen</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550839">MRxTruncate</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550844">MRxZeroExtend</a>
</dt>
<dt>
<a href="..\fcb\nf-fcb-rxfinalizesrvopen.md">RxFinalizeSrvOpen</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20MRxForceClosed routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

