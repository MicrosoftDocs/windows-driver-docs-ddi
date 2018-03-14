---
UID: NF:fcb.RxFinalizeSrvOpen
title: RxFinalizeSrvOpen function
author: windows-driver-content
description: RxFinalizeSrvOpen finalizes the given SRV_OPEN structure. The caller must have an exclusive lock on the FCB associated with the SRV_OPEN and either a shared or exclusive lock on the table lock of the NET_ROOT associated with the FCB.
old-location: ifsk\rxfinalizesrvopen.htm
old-project: ifsk
ms.assetid: 9a756606-90df-4bb8-a87a-f000616812fa
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RxFinalizeSrvOpen, RxFinalizeSrvOpen function [Installable File System Drivers], fcb/RxFinalizeSrvOpen, ifsk.rxfinalizesrvopen, rxref_0665a600-9a4c-4674-87bd-f9758b579cee.xml
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
-	RxFinalizeSrvOpen
product: Windows
targetos: Windows
req.typenames: FA_ENTRY, *PFA_ENTRY
---

# RxFinalizeSrvOpen function


## -description


<b>RxFinalizeSrvOpen</b> finalizes the given SRV_OPEN structure. The caller must have an exclusive lock on the FCB associated with the SRV_OPEN and either a shared or exclusive lock on the table lock of the NET_ROOT associated with the FCB.


## -syntax


````
BOOLEAN RxFinalizeSrvOpen(
  _Out_ PSRV_OPEN ThisSrvOpen,
  _In_  BOOLEAN   RecursiveFinalize,
  _In_  BOOLEAN   ForceFinalize
);
````


## -parameters




### -param ThisSrvOpen [out]

A pointer to the SRV_OPEN structure to finalize.


### -param RecursiveFinalize [in]

The value indicating whether the finalization should be done recursively. 


### -param ForceFinalize [in]

The value indicating whether the finalization should be forced, regardless of the reference count. 

If <i>ForceFinalize</i> is <b>FALSE</b>, then the <b>NodeReferenceCount</b> member of the SRV_OPEN structure pointed to by <i>ThisSrvOpen</i> must be 0 for the SRV_OPEN to be finalized. 


## -returns



<b>RxFinalizeSrvOpen</b> returns <b>TRUE</b> on success or <b>FALSE</b> if the finalization did not occur: 




## -remarks



The <b>RxFinalizeSrvOpen</b> routine is not normally called by network mini-redirector drivers directly. RDBSS calls this routine internally when the reference count on the SRV_OPEN is decremented to 1. RDBSS also calls <b>RxFinalizeSrvOpen</b> when the <b>RxFinalizeNetFcb </b>routine is called with the <i>RecursiveFinalize</i> set to <b>TRUE</b>. RDBSS calls <b>RxFinalizeNetFcb</b> when an I/O request packet is received for IRP_MJ_CLOSE. This IRP is normally received by RDBSS in response to a user-mode application requesting a file close operation. It is also possible for another kernel driver to issue such an IRP. 

Before calling <b>RxFinalizeSrvOpen</b>, the caller must have acquired an exclusive lock on the FCB associated with the SRV_OPEN and acquired either a shared or exclusive lock on the table lock of the NET_ROOT associated with the FCB. 

If the <i>RecursiveFinalize</i> parameter is <b>TRUE</b>, then <b>RxFinalizeSrvOpen</b> will finalize any FOBX structures associated with this SRV_OPEN by calling <b>RxFinalizeNetFobx</b> with the <i>RecursiveFinalize </i>parameter set to <b>TRUE</b> and the <i>ForceFinalize</i> parameter. 

If the <b>FcbState</b> member of the associated FCB does not have the FCB_STATE_ORPHANED flag set, then <b>RxFinalizeSrvCall</b> will call the <b>MRxForceClosed</b> routine provided by the network mini-redirector to finalize the SRV_CALL. If the SRV_CALL structure was not originally allocated as part of creating the FCB, then the memory for the SRV_CALL structure will also be released. 




## -see-also

<a href="..\fcb\nf-fcb-rxcreatenetfobx.md">RxCreateNetFobx</a>



<a href="..\mrx\nc-mrx-pmrx_forceclosed_calldown.md">MRxForceClosed</a>



<a href="..\rxprocs\nf-rxprocs-rxsetsrvcalldomainname.md">RxSetSrvCallDomainName</a>



<a href="..\fcb\nf-fcb-rxfinishfcbinitialization.md">RxFinishFcbInitialization</a>



<a href="..\fcb\nf-fcb-rxfinalizenetfobx.md">RxFinalizeNetFobx</a>



<a href="..\fcb\nf-fcb-rxcreatenetroot.md">RxCreateNetRoot</a>



<a href="..\fcb\nf-fcb-rxpreferencenetfcb.md">RxpReferenceNetFcb</a>



<a href="..\rxprocs\nf-rxprocs-rxdereference.md">RxDereference</a>



<a href="..\fcb\nf-fcb-rxcreatevnetroot.md">RxCreateVNetRoot</a>



<a href="..\fcb\nf-fcb-rxcreatesrvcall.md">RxCreateSrvCall</a>



<a href="https://msdn.microsoft.com/6cf4c6f6-a21f-4919-92b5-2403b650d8d0">The SRV_OPEN Structure</a>



<a href="..\rxprocs\nf-rxprocs-rxforcefinalizeallvnetroots.md">RxForceFinalizeAllVNetRoots</a>



<a href="..\rxprocs\nf-rxprocs-rxfinalizenetfcb.md">RxFinalizeNetFcb</a>



<a href="..\fcb\nf-fcb-rxcreatesrvopen.md">RxCreateSrvOpen</a>



<a href="..\fcb\nf-fcb-rxcreatenetfcb.md">RxCreateNetFcb</a>



<a href="..\fcb\nf-fcb-rxpdereferencenetfcb.md">RxpDereferenceNetFcb</a>



<a href="..\rxprocs\nf-rxprocs-rxfinalizeconnection.md">RxFinalizeConnection</a>



<a href="..\fcb\nf-fcb-rxfinalizenetroot.md">RxFinalizeNetRoot</a>



<a href="..\fcb\nf-fcb-rxfinalizesrvcall.md">RxFinalizeSrvCall</a>



<a href="..\rxprocs\nf-rxprocs-rxreference.md">RxReference</a>



<a href="..\fcb\nf-fcb-rxfinalizevnetroot.md">RxFinalizeVNetRoot</a>



 

 


