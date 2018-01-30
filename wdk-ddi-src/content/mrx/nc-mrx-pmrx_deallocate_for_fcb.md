---
UID: NC:mrx.PMRX_DEALLOCATE_FOR_FCB
title: PMRX_DEALLOCATE_FOR_FCB
author: windows-driver-content
description: The MRxDeallocateForFcb routine is called by RDBSS to request that the network mini-redirector deallocate an FCB structure. This call is in response to a request to close a file system object.
old-location: ifsk\mrxdeallocateforfcb.htm
old-project: ifsk
ms.assetid: 4347f481-cd8f-4a88-92e0-f6bc7a4b7ffb
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.mrxdeallocateforfcb, MRxDeallocateForFcb routine [Installable File System Drivers], MRxDeallocateForFcb, PMRX_DEALLOCATE_FOR_FCB, PMRX_DEALLOCATE_FOR_FCB, mrx/MRxDeallocateForFcb, mrxref_02a9e4a3-db00-48e1-ac2e-cd6a47ae4c37.xml
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
-	MRxDeallocateForFcb
product: Windows
targetos: Windows
req.typenames: "*PSetDSMCounters_IN, SetDSMCounters_IN"
---

# PMRX_DEALLOCATE_FOR_FCB callback


## -description


The<i> MRxDeallocateForFcb</i> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that the network mini-redirector deallocate an FCB structure. This call is in response to a request to close a file system object.


## -prototype


````
PMRX_DEALLOCATE_FOR_FCB MRxDeallocateForFcb;

NTSTATUS MRxDeallocateForFcb(
  _Inout_ PMRX_FCB pFcb
)
{ ... }
````


## -parameters




### -param Fcb






#### - pFcb [in, out]

A pointer to the FCB structure to deallocate.


## -returns


<i>MRxDeallocateForFcb</i> returns STATUS_SUCCESS.



## -remarks


<i>MRxDeallocateForFcb</i> is called by <a href="..\rxprocs\nf-rxprocs-rxfinalizenetfcb.md">RxFinalizeNetFCB</a> as part of the process to finalize an FCB structure. The calls to <b>RxFinalizeNetFCB</b> and <i>MRxDeallocateForFcb</i> occur when an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550720">IRP_MJ_CLOSE</a> request is received.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549862">MRxCreate</a>

<a href="..\mrx\nc-mrx-pmrx_chkfcb_calldown.md">MRxAreFilesAliased</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549872">MRxDeallocateForFobx</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550817">MRxShouldTryToCollapseThisOpen</a>

<a href="..\mrx\nc-mrx-pmrx_calldown.md">MRxCloseSrvOpen</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549841">MRxCleanupFobx</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549878">MRxExtendForCache</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550844">MRxZeroExtend</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550839">MRxTruncate</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550669">MRxFlush</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549847">MRxCollapseOpen</a>

<a href="..\rxprocs\nf-rxprocs-rxfinalizenetfcb.md">RxFinalizeNetFCB</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550677">MRxForceClosed</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549879">MRxExtendForNonCache</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550691">MRxIsLockRealizable</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20MRxDeallocateForFcb routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

