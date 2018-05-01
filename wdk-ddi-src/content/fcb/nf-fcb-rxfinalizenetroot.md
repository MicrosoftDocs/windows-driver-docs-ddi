---
UID: NF:fcb.RxFinalizeNetRoot
title: RxFinalizeNetRoot function
author: windows-driver-content
description: RxFinalizeNetRoot finalizes the given NET_ROOT structure. The caller must have an exclusive lock on the netname table associated with the device object.
old-location: ifsk\rxfinalizenetroot.htm
old-project: ifsk
ms.assetid: f0566902-b85b-4676-9f8f-67749ce2060a
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: RxFinalizeNetRoot, RxFinalizeNetRoot function [Installable File System Drivers], fcb/RxFinalizeNetRoot, ifsk.rxfinalizenetroot, rxref_66fb454b-96a0-401b-b184-0c24510bfaf6.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fcb.h
req.include-header: Fcb.h, Mrxfcb.h
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fcb.h
api_name:
-	RxFinalizeNetRoot
product: Windows
targetos: Windows
req.typenames: 
---

# RxFinalizeNetRoot function


## -description


<b>RxFinalizeNetRoot</b> finalizes the given NET_ROOT structure. The caller must have an exclusive lock on the netname table associated with the device object. 


## -parameters




### -param ThisNetRoot [out]

A pointer to the NET_ROOT structure to finalize.


### -param RecursiveFinalize [in]

The value indicating whether the finalization should be done recursively. 


### -param ForceFinalize [in]

The value indicating whether the finalization should be forced, regardless of the reference count. 

If <i>ForceFinalize</i> is <b>FALSE</b>, then the <b>NodeReferenceCount</b> member of the NET_ROOT strcuture pointed to by <i>ThisNetRoot </i>must be 1 for the NET_ROOT to be finalized. 


## -returns



<b>RxFinalizeNetRoot</b> returns <b>TRUE</b> on success or <b>FALSE</b> if the finalization did not occur: If a finalization of the NET_ROOT is already in process, <b>RxFinalizeNetRoot</b> will return <b>FALSE</b>.




## -remarks



The <b>RxFinalizeNetRoot</b> routine is not normally called by network mini-redirector drivers directly. RDBSS calls this routine internally when the reference count on the NET_ROOT is decremented to 1.

Before calling <b>RxFinalizeNetRoot</b>, a lock on the netname table associated with the device object must be acquired in exclusive mode. 

If the <i>RecursiveFinalize</i> parameter is <b>TRUE</b>, then <b>RxFinalizeNetRoot</b> will purge any orphaned FCB structures associated with this NET_ROOT. These ophaned FCBs are structures where the <b>FcbState</b> member has the FCB_STATE_ORPHANED flag set on. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554356">RxCreateNetFcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554358">RxCreateNetFobx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554366">RxCreateNetRoot</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554370">RxCreateSrvCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554376">RxCreateSrvOpen</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554380">RxCreateVNetRoot</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554388">RxDereference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554409">RxFinalizeConnection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554412">RxFinalizeNetFcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554418">RxFinalizeNetFobx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554426">RxFinalizeSrvCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554432">RxFinalizeSrvOpen</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554450">RxFinalizeVNetRoot</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554454">RxFinishFcbInitialization</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554463">RxForceFinalizeAllVNetRoots</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554688">RxReference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554728">RxSetSrvCallDomainName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554608">RxpDereferenceNetFcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554627">RxpReferenceNetFcb</a>



<a href="https://msdn.microsoft.com/f7846343-9af6-4b7f-9c8d-190abb524946">The NET_ROOT Structure</a>
 

 

