---
UID: NF:fcb.RxCreateNetFobx
title: RxCreateNetFobx function (fcb.h)
description: RxCreateNetFobx allocates, initializes, and inserts a new file object extension (FOBX) structure into the in-memory data structures for a FCB that this FOBX is being opened on.
old-location: ifsk\rxcreatenetfobx.htm
tech.root: ifsk
ms.assetid: 4ea03ea5-31df-4220-982c-0102d20c2d4a
ms.date: 04/16/2018
keywords: ["RxCreateNetFobx function"]
ms.keywords: RxCreateNetFobx, RxCreateNetFobx function [Installable File System Drivers], fcb/RxCreateNetFobx, ifsk.rxcreatenetfobx, rxref_851152a8-bc89-44f8-9e74-1621e425dbba.xml
f1_keywords:
 - "fcb/RxCreateNetFobx"
 - "RxCreateNetFobx"
req.header: fcb.h
req.include-header: Rxcontx.h, Mrxfcb.h, Fcb.h
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
- RxCreateNetFobx
targetos: Windows
req.typenames: 
---

# RxCreateNetFobx function


## -description


<b>RxCreateNetFobx</b> allocates, initializes, and inserts a new file object extension (FOBX) structure into the in-memory data structures for a FCB that this FOBX is being opened on. 


## -parameters




### -param RxContext [out]

A pointer to the RX_CONTEXT structure describing a create operation.


### -param MrxSrvOpen [in]

A pointer to the associated SRV_OPEN structure.


## -returns



<b>RxCreateNetFobx</b> returns a pointer to a newly allocated FOBX data structure on success or a <b>NULL</b> pointer on failure. 




## -remarks



Network mini-redirectors should call <b>RxCreateNetFobx</b> to create an FOBX at the end of a successful create operation.

Before calling <b>RxCreateNetFobx</b>, the FCB associated with the FOBX structure must be acquired in exclusive mode. 

<b>RxCreateNetFobx </b>will try and use the FOBX allocated as part of the associated FCB structure if it is available. If the FOBX allocated with the FCB is not available, then <b>RxCreateNetFobx </b>will try and use the FOBX allocated as part of the associated SRV_OPEN structure if it is available. In either of these cases, <b>RxCreateNetFobx</b> only needs to initialize the existing FOBX structure, no memory allocation is required. If both of the FOBX structures on the associated FCB and SRV_OPEN structure are not available, then <b>RxCreateNetFobx</b> will allocate a new FOBX structure. 

If the associated FCB is a paging file, <b>RxCreateNetFobx</b> allocates non-paged pool memory when creating the new FOBX data structure. If the associated FCB is a not a paging file, <b>RxCreateNetFobx</b> allocates paged pool memory when creating the new FOBX data structure.

Windows does not currently allow having a paging file on a remote machine.

On success, the following FOBX members in the FOBX structure are set:

<ul>
<li>
The <b>NodeReference</b> member is set to 1.

</li>
<li>
The <b>FobxSerialNumber</b> member is set to 0.

</li>
<li>
The <b>SrvOpen</b> member is set to the associated SRV_OPEN structure.

</li>
<li>
The <b>fOpenCountDecremented</b> member is set to <b>FALSE</b>.

</li>
<li>
The <b>Flags</b> member is set to a value based on parameters from the RX_CONTEXT and whether a new FOBX needed to be allocated. 

</li>
</ul>
On success, the reference count for the SRV_OPEN structure is incremented and the <b>NumberOfFobxs</b> member on the associated V_NET_ROOT structure is incremented. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/ns-rxcontx-_rx_context">RX_CONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatenetfcb">RxCreateNetFcb</a>



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



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizesrvopen">RxFinalizeSrvOpen</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizevnetroot">RxFinalizeVNetRoot</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinishfcbinitialization">RxFinishFcbInitialization</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxforcefinalizeallvnetroots">RxForceFinalizeAllVNetRoots</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxreference">RxReference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxsetsrvcalldomainname">RxSetSrvCallDomainName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxpdereferencenetfcb">RxpDereferenceNetFcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxpreferencenetfcb">RxpReferenceNetFcb</a>
 

 

