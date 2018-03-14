---
UID: NA:fcb
ms.assetid: 31bd7560-81fd-3e7e-a47c-c76a4117f5fb
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Fcb.h header



This header is used by Installable file system. For more information, see
- [Installable file system](../_ifsk/index.md)

Fcb.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [RxCreateNetFcb function](nf-fcb-rxcreatenetfcb.md) | RxCreateNetFCB allocates, initializes, and inserts a new FCB structure into the in-memory data structures for a V_NET_ROOT that this FCB is being opened on. The structure allocated has space for a SRV_OPEN and an FOBX structure. |
| [RxCreateNetFobx function](nf-fcb-rxcreatenetfobx.md) | RxCreateNetFobx allocates, initializes, and inserts a new file object extension (FOBX) structure into the in-memory data structures for a FCB that this FOBX is being opened on. |
| [RxCreateNetRoot function](nf-fcb-rxcreatenetroot.md) | RxCreateNetRoot allocates and initializes a NET_ROOT structure and inserts the name into the net name table on the associated device object. |
| [RxCreateSrvCall function](nf-fcb-rxcreatesrvcall.md) | RxCreateSrvCall builds a SRV_CALL structure and inserts the name into the net name table maintained by RDBSS. |
| [RxCreateSrvOpen function](nf-fcb-rxcreatesrvopen.md) | RxCreateSrvOpen allocates, initializes, and inserts a new SRV_OPEN structure into the in-memory data structures used by RDBSS. If a new structure has to be allocated, it has space for an FOBX structure. |
| [RxCreateVNetRoot function](nf-fcb-rxcreatevnetroot.md) | RxCreateVNetRoot allocates and initializes a NET_ROOT structure and inserts the name into the net name table on the associated device object. |
| [RxFinalizeNetFobx function](nf-fcb-rxfinalizenetfobx.md) | RxFinalizeNetFOBX finalizes the given FOBX structure. The caller must have an exclusive lock on the FCB associated with FOBX structure. |
| [RxFinalizeNetRoot function](nf-fcb-rxfinalizenetroot.md) | RxFinalizeNetRoot finalizes the given NET_ROOT structure. The caller must have an exclusive lock on the netname table associated with the device object. |
| [RxFinalizeSrvCall function](nf-fcb-rxfinalizesrvcall.md) | RxFinalizeSrvCall finalizes the given SRV_CALL structure. The caller must have an exclusive lock on the netname table associated with the device object. |
| [RxFinalizeSrvOpen function](nf-fcb-rxfinalizesrvopen.md) | RxFinalizeSrvOpen finalizes the given SRV_OPEN structure. The caller must have an exclusive lock on the FCB associated with the SRV_OPEN and either a shared or exclusive lock on the table lock of the NET_ROOT associated with the FCB. |
| [RxFinalizeVNetRoot function](nf-fcb-rxfinalizevnetroot.md) | RxFinalizeVNetRoot finalizes the given V_NET_ROOT structure. The caller must have an exclusive lock on the netname table associated with the device object. |
| [RxFinishFcbInitialization function](nf-fcb-rxfinishfcbinitialization.md) | RxFinishFcbInitialization is used to finish initializing an FCB after the successful completion of a create operation by the network mini-redirector. |
| [RxGetFileSizeWithLock function](nf-fcb-rxgetfilesizewithlock.md) | RxGetFileSizeWithLock gets the file size in the FCB structure using a lock to ensure that the 64-bit value is read consistently. |
| [RxInferFileType function](nf-fcb-rxinferfiletype.md) | RxInferFileType tries to infer the file type (directory or non-directory) from a member in the RX_CONTEXT structure. |
| [RxpDereferenceAndFinalizeNetFcb function](nf-fcb-rxpdereferenceandfinalizenetfcb.md) | RxpDereferenceAndFinalizeNetFcb decrements the reference count and finalizes an FCB structure. |
| [RxpDereferenceNetFcb function](nf-fcb-rxpdereferencenetfcb.md) | RxpDereferenceNetFcb decrements the reference count on an FCB structure. |
| [RxpReferenceNetFcb function](nf-fcb-rxpreferencenetfcb.md) | RxpReferenceNetFcb increments the reference count on an FCB. |
| [RxpTrackDereference function](nf-fcb-rxptrackdereference.md) | RxpTrackDereference is used in checked builds to track requests to dereference SRV_CALL, NET_ROOT, V_NET_ROOT, FOBX, FCB, and SRV_OPEN structures in checked builds. A log of these dereference requests can be accessed by the logging system and WMI. |
| [RxpTrackReference function](nf-fcb-rxptrackreference.md) | RxpTrackReference tracks requests to reference SRV_CALL, NET_ROOT, V_NET_ROOT, FOBX, FCB, and SRV_OPEN structures in checked builds. A log of these reference requests can be accessed by the logging system and WMI. |
