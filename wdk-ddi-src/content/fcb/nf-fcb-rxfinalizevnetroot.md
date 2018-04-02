---
UID: NF:fcb.RxFinalizeVNetRoot
title: RxFinalizeVNetRoot function
author: windows-driver-content
description: RxFinalizeVNetRoot finalizes the given V_NET_ROOT structure. The caller must have an exclusive lock on the netname table associated with the device object.
old-location: ifsk\rxfinalizevnetroot.htm
old-project: ifsk
ms.assetid: 7a24d8b4-cd07-453c-9813-d794b75b039e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RxFinalizeVNetRoot, RxFinalizeVNetRoot function [Installable File System Drivers], fcb/RxFinalizeVNetRoot, ifsk.rxfinalizevnetroot, rxref_1c20872c-4783-4c7d-a1fa-44ca6170ab00.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fcb.h
req.include-header: Mrxfcb.h, Fcb.h
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
-	RxFinalizeVNetRoot
product:
- Windows
targetos: Windows
req.typenames: FA_ENTRY, *PFA_ENTRY
---

# RxFinalizeVNetRoot function


## -description


<b>RxFinalizeVNetRoot</b> finalizes the given V_NET_ROOT structure. The caller must have an exclusive lock on the netname table associated with the device object. 


## -parameters




### -param ThisVNetRoot [out]

A pointer to the V_NET_ROOT structure to finalize.


### -param RecursiveFinalize [in]

The value indicating whether the finalization should be done recursively. This parameter in not currently used.


### -param ForceFinalize [in]

The value indicating whether the finalization should be forced, regardless of the reference count. 

If <i>ForceFinalize</i> is <b>FALSE</b>, then the <b>NodeReferenceCount</b> member of the V_NET_ROOT structure pointed to by <i>ThisVNetRoot</i> must be 1 for the V_NET_ROOT to be finalized. 


## -returns



<b>RxFinalizeVNetRoot</b> returns <b>TRUE</b> on success or <b>FALSE</b> if the finalization did not occur: 




## -remarks



The <b>RxFinalizeVNetRoot</b> routine is not normally called by network mini-redirector drivers directly. RDBSS calls this routine internally when the reference count on the V_NET_ROOT is decremented to 1. 

<b>RxFinalizeVNetRoot</b> is also called by the <b>RxFinalizeConnection</b> routine if the <i>Level</i> parameter to <b>RxFinalizeConnection</b> is set to <b>TRUE</b>. <b>RxFinalizeConnection</b> is normally called by a network mini-redirector driver in response to receiving a custom IOCTL request from user mode. For example, a user might execute from the command line a "NET USE x: /d" to delete a share. This request would be mapped through the network provider DLL provided by the network mini-redirector to a custom IOCTL request sent to the network mini-redirector kernel driver which would call the <b>RxFinalizeConnection</b> routine to delete the connection and any associated V_NET_ROOT structures.

<b>RxFinalizeVNetRoot</b> is also called by the <b>RxForceFinalizeAllVNetRoots</b> routine to finalize each V_NET_ROOT associated with a NET_ROOT structure.

Before calling <b>RxFinalizeVNetRoot</b>, a lock on the netname table associated with the device object must be acquired in exclusive mode. 

If the <b>UpperFinalization</b> member of the V_NET_ROOT is 0, then <b>RxFinalizeVNetRoot</b> will iterate through all the FCBs that belong to the NET_ROOT associated with this V_NET_ROOT and orphan all of the SRV_OPEN structures that are associated with the V_NET_ROOT. 

<b>RxFinalizeVNetRoot</b> will call the <b>MRxFinalizeVNetRoot</b> routine provided by the network mini-redirector to finalize the V_NET_ROOT before the memory for the V_NET_ROOT structure will be released. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550663">MRxFinalizeVNetRoot</a>



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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554421">RxFinalizeNetRoot</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554426">RxFinalizeSrvCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554432">RxFinalizeSrvOpen</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554454">RxFinishFcbInitialization</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554463">RxForceFinalizeAllVNetRoots</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554688">RxReference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554728">RxSetSrvCallDomainName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554608">RxpDereferenceNetFcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554627">RxpReferenceNetFcb</a>



<a href="https://msdn.microsoft.com/866eba91-13b6-4b15-93de-4f627a635c92">The V_NET_ROOT Structure</a>
 

 

