---
UID: NF:fcb.RxCreateNetRoot
title: RxCreateNetRoot function (fcb.h)
description: RxCreateNetRoot allocates and initializes a NET_ROOT structure and inserts the name into the net name table on the associated device object.
old-location: ifsk\rxcreatenetroot.htm
tech.root: ifsk
ms.assetid: 076624d3-96f5-4e93-8598-b880a6b2289b
ms.date: 04/16/2018
keywords: ["RxCreateNetRoot function"]
ms.keywords: RxCreateNetRoot, RxCreateNetRoot function [Installable File System Drivers], fcb/RxCreateNetRoot, ifsk.rxcreatenetroot, rxref_3171aa4b-bf5b-4114-a5a0-40af765b09da.xml
req.header: fcb.h
req.include-header: Rxcontx.h, Mrxfcb.h, Prefix.h, Struchdr.h, Fcb.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - RxCreateNetRoot
 - fcb/RxCreateNetRoot
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - fcb.h
api_name:
 - RxCreateNetRoot
---

# RxCreateNetRoot function


## -description

<b>RxCreateNetRoot</b> allocates and initializes a NET_ROOT structure and inserts the name into the net name table on the associated device object.

## -parameters

### -param SrvCall 

[in]
A pointer to the associated SRV_CALL structure.

### -param Name 

[in]
A pointer to the name to be inserted in the name table.

### -param NetRootFlags 

[in]
The value to set the <b>Flags</b> member of the NET_ROOT which is used to denote the state of the NET_ROOT structure.

### -param RxConnectionId 

[in, optional]
A pointer to the connection ID to be associated with the name to be inserted in the prefix name table. This parameter can be <b>NULL</b> in which case no connection ID will be associated with the name inserted in the prefix name table.

## -returns

<b>RxCreateNetRoot</b> returns a pointer to a newly created NET_ROOT data structure on success or a <b>NULL</b> pointer on failure.

## -remarks

The <b>RxCreateNetRoot</b> routine is not normally called by network mini-redirector drivers directly. RDBSS calls this routine internally when an I/O request packet is received for IRP_MJ_CREATE and a NET_ROOT needs to be created. This IRP is normally received by RDBSS in response to a user-mode application requesting a file create operation on a network share. It is also possible for another kernel driver to issue such an IRP. 

Before calling <b>RxCreateNetRoot</b>, a lock on the name table associated with the device object member of the <i>SrvCall</i> parameter must be acquired in exclusive mode. 

The NET_ROOT flags are split into two groups, those visible to network mini redirectors and those invisible to network mini redirectors. The visible ones are the lower 16-bits of the <b>Flags</b> member of the NET_ROOT. This routine does not check or test which flags are being set. 

On success, the reference count for the SRV_CALL structure is incremented.

## -see-also

<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatenetfcb">RxCreateNetFcb</a>



<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatenetfobx">RxCreateNetFobx</a>



<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatesrvcall">RxCreateSrvCall</a>



<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatesrvopen">RxCreateSrvOpen</a>



<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatevnetroot">RxCreateVNetRoot</a>



<a href="/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxdereference">RxDereference</a>



<a href="/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxfinalizeconnection">RxFinalizeConnection</a>



<a href="/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxfinalizenetfcb">RxFinalizeNetFcb</a>



<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizenetfobx">RxFinalizeNetFobx</a>



<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizenetroot">RxFinalizeNetRoot</a>



<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizesrvcall">RxFinalizeSrvCall</a>



<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizesrvopen">RxFinalizeSrvOpen</a>



<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizevnetroot">RxFinalizeVNetRoot</a>



<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinishfcbinitialization">RxFinishFcbInitialization</a>



<a href="/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxforcefinalizeallvnetroots">RxForceFinalizeAllVNetRoots</a>



<a href="/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxreference">RxReference</a>



<a href="/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxsetsrvcalldomainname">RxSetSrvCallDomainName</a>



<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxpdereferencenetfcb">RxpDereferenceNetFcb</a>



<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxpreferencenetfcb">RxpReferenceNetFcb</a>



<a href="/windows-hardware/drivers/ifs/the-net-root-structure">The NET_ROOT Structure</a>



<a href="/windows-hardware/drivers/ifs/the-srv-call-structure">The SRV_CALL Structure</a>