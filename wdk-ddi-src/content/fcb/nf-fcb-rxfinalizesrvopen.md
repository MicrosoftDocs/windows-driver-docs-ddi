---
UID: NF:fcb.RxFinalizeSrvOpen
title: RxFinalizeSrvOpen function (fcb.h)
description: RxFinalizeSrvOpen finalizes the given SRV_OPEN structure. The caller must have an exclusive lock on the FCB associated with the SRV_OPEN and either a shared or exclusive lock on the table lock of the NET_ROOT associated with the FCB.
old-location: ifsk\rxfinalizesrvopen.htm
tech.root: ifsk
ms.assetid: 9a756606-90df-4bb8-a87a-f000616812fa
ms.date: 04/16/2018
keywords: ["RxFinalizeSrvOpen function"]
ms.keywords: RxFinalizeSrvOpen, RxFinalizeSrvOpen function [Installable File System Drivers], fcb/RxFinalizeSrvOpen, ifsk.rxfinalizesrvopen, rxref_0665a600-9a4c-4674-87bd-f9758b579cee.xml
f1_keywords:
 - "fcb/RxFinalizeSrvOpen"
 - "RxFinalizeSrvOpen"
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- fcb.h
api_name:
- RxFinalizeSrvOpen
targetos: Windows
req.typenames: 
---

# RxFinalizeSrvOpen function


## -description


<b>RxFinalizeSrvOpen</b> finalizes the given SRV_OPEN structure. The caller must have an exclusive lock on the FCB associated with the SRV_OPEN and either a shared or exclusive lock on the table lock of the NET_ROOT associated with the FCB.


## -parameters




### -param ThisSrvOpen 
[out]
A pointer to the SRV_OPEN structure to finalize.


### -param RecursiveFinalize 
[in]
The value indicating whether the finalization should be done recursively. 


### -param ForceFinalize 
[in]
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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_forceclosed_calldown">MRxForceClosed</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatenetfcb">RxCreateNetFcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatenetfobx">RxCreateNetFobx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatenetroot">RxCreateNetRoot</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatesrvcall">RxCreateSrvCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatesrvopen">RxCreateSrvOpen</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatevnetroot">RxCreateVNetRoot</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxdereference">RxDereference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxfinalizeconnection">RxFinalizeConnection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxfinalizenetfcb">RxFinalizeNetFcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizenetfobx">RxFinalizeNetFobx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizenetroot">RxFinalizeNetRoot</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizesrvcall">RxFinalizeSrvCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizevnetroot">RxFinalizeVNetRoot</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinishfcbinitialization">RxFinishFcbInitialization</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxforcefinalizeallvnetroots">RxForceFinalizeAllVNetRoots</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxreference">RxReference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxsetsrvcalldomainname">RxSetSrvCallDomainName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxpdereferencenetfcb">RxpDereferenceNetFcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxpreferencenetfcb">RxpReferenceNetFcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/the-srv-open-structure">The SRV_OPEN Structure</a>
 

 

