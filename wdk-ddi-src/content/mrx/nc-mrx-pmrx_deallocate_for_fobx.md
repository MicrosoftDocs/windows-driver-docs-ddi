---
UID: NC:mrx.PMRX_DEALLOCATE_FOR_FOBX
title: PMRX_DEALLOCATE_FOR_FOBX
author: windows-driver-content
description: The MRxDeallocateForFobx routine is called by RDBSS to request that the network mini-redirector deallocate an FOBX structure. This call is in response to a request to close a file system object.
old-location: ifsk\mrxdeallocateforfobx.htm
tech.root: ifsk
ms.assetid: 3b33df22-7757-4270-8cb0-59e8f5d5a80a
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: MRxDeallocateForFobx, MRxDeallocateForFobx routine [Installable File System Drivers], PMRX_DEALLOCATE_FOR_FOBX, ifsk.mrxdeallocateforfobx, mrx/MRxDeallocateForFobx, mrxref_2b2fa1f1-19f9-4a9b-9105-7c5946428b88.xml
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
-	MRxDeallocateForFobx
product:
- Windows
targetos: Windows
req.typenames: 
---

# PMRX_DEALLOCATE_FOR_FOBX callback function


## -description


The<i> MRxDeallocateForFobx</i> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that the network mini-redirector deallocate an FOBX structure. This call is in response to a request to close a file system object.


## -parameters




### -param Fobx








#### - pFobx [in, out]

A pointer to the FOBX structure to deallocate.


## -returns



<i>MRxDeallocateForFobx</i> returns STATUS_SUCCESS.




## -remarks



<i>MRxDeallocateForFobx</i> is called by <a href="https://msdn.microsoft.com/library/windows/hardware/ff554418">RxFinalizeNetFOBX</a> as part of the process to finalize an FOBX structure. The calls to <b>RxFinalizeNetFOBX</b> and <i>MRxDeallocateForFobx</i> occurs when an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550720">IRP_MJ_CLOSE</a> request is received.

RDBSS ignores the return value from <i>MRxDeallocateForFobx</i>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549838">MRxAreFilesAliased</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549841">MRxCleanupFobx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549845">MRxCloseSrvOpen</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549847">MRxCollapseOpen</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549862">MRxCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549871">MRxDeallocateForFcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549872">MRxDeallocateForFobx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549878">MRxExtendForCache</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549879">MRxExtendForNonCache</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550669">MRxFlush</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550677">MRxForceClosed</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550691">MRxIsLockRealizable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550817">MRxShouldTryToCollapseThisOpen</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550839">MRxTruncate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550844">MRxZeroExtend</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554418">RxFinalizeNetFOBX</a>
 

 

