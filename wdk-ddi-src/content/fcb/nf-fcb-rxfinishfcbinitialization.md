---
UID: NF:fcb.RxFinishFcbInitialization
title: RxFinishFcbInitialization function (fcb.h)
description: Learn more about the RxFinishFcbInitialization function.
tech.root: ifsk
ms.date: 10/05/2023
keywords: ["RxFinishFcbInitialization function"]
ms.keywords: RDBSS_NTC_MAILSLOT, RDBSS_NTC_SPOOLFILE, RDBSS_NTC_STORAGE_TYPE_DIRECTORY, RDBSS_NTC_STORAGE_TYPE_FILE, RDBSS_NTC_STORAGE_TYPE_UNKNOWN, RxFinishFcbInitialization, RxFinishFcbInitialization function [Installable File System Drivers], fcb/RxFinishFcbInitialization, ifsk.rxfinishfcbinitialization, rxref_436f96f7-35ed-484b-8963-4afa559d3cfb.xml
req.header: fcb.h
req.include-header: Mrxfcb.h, Nodetype.h, Fcb.h
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
 - RxFinishFcbInitialization
 - fcb/RxFinishFcbInitialization
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - fcb.h
api_name:
 - RxFinishFcbInitialization
---

# RxFinishFcbInitialization function

## -description

**RxFinishFcbInitialization** is used to finish initializing an FCB after the successful completion of a create operation by the network mini-redirector.

## -parameters

### -param Fcb

A pointer to the MRX_FCB structure being initialized.

### -param FileType

The value indicating the storage type of entity that the FCB refers to. Possible options for this parameter include the following:

| Value | Meaning |
| ----- | ------- |
| RDBSS_NTC_MAILSLOT               | A mail slot. |
| RDBSS_NTC_SPOOLFILE              | A printer spool file. |
| RDBSS_NTC_STORAGE_TYPE_DIRECTORY | A directory. |
| RDBSS_NTC_STORAGE_TYPE_UNKNOWN   | The storage type is unknown. |
| RDBSS_NTC_STORAGE_TYPE_FILE      | A file. |

### -param InitPacket

Pointer to extra data that is required for initialization depending on the storage type of the FCB being initialized. This parameter may be a **NULL** pointer if no extra data is provided.

## -remarks

When called as a result of an IRP_MJ_CREATE, <a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatenetfcb">RxCreateNetFCB</a> is called first to create the FCB. If the **Type** member of the NET_ROOT to be created is not a NET_ROOT_MAILSLOT, then **RxFinishFcbInitialization** is called to finish the initialization of the FCB structure.

If the **FcbState** member of the MRX_FCB structure pointed to by **MrxFcb** does not have the FCB_STATE_TIME_AND_SIZE_ALREADY_SET on, then the following members of the FCB will be updated from the **InitPacket** parameter if **InitPacket** is non **NULL**: **Attributes**, **NumberOfLinks**, **CreationTime**, **LastAccessTime**, **LastWriteTime**, **LastChangeTime**, **ActualAllocationLength**, **Header.AllocationSize**, **Header.FileSize**, and **Header.ValidDataLength**. The FCB_STATE_TIME_AND_SIZE_ALREADY_SET option is then set on in the **FcbState** member of the FCB structure.

If the storage type is an RDBSS_NTC_MAILSLOT and the FcbState member of the FCB does have the FCB_STATE_TIME_AND_SIZE_ALREADY_SET option set on, then the following members of the FCB structure for the mail slot will be initialized to 0: **Attributes**, **NumberOfLinks**, **CreationTime.QuadPart**, **LastAccessTime.QuadPart**, **LastWriteTime.QuadPart**, **LastChangeTime**.**QuadPart**, **ActualAllocationLength**, **Header.AllocationSize.QuadPart**, **Header.FileSize.QuadPart**, and **Header.ValidDataLength.QuadPart**

## -see-also

<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatenetfcb">RxCreateNetFCB</a>

<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatenetfobx">RxCreateNetFobx</a>

<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatenetroot">RxCreateNetRoot</a>

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

<a href="/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxforcefinalizeallvnetroots">RxForceFinalizeAllVNetRoots</a>

<a href="/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxreference">RxReference</a>

<a href="/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxsetsrvcalldomainname">RxSetSrvCallDomainName</a>

<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxpdereferencenetfcb">RxpDereferenceNetFcb</a>

<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxpreferencenetfcb">RxpReferenceNetFcb</a>
