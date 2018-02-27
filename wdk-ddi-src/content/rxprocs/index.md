---
UID: NA:rxprocs
ms.assetid: 9182db0e-0b5c-3344-9496-2d7af4c52636
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Rxprocs.h header



This header is used by Installable file system. For more information, see
- [Installable file system](../_ifsk/index.md)

Rxprocs.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [RxChangeBufferingState function](nf-rxprocs-rxchangebufferingstate.md) | RxChangeBufferingState is called to process a buffering state change request. |
| [RxCompleteRequest function](nf-rxprocs-rxcompleterequest.md) | RxCompleteRequest completes the IRP request associated with an RX_CONTEXT structure. |
| [RxCompleteRequest_Real function](nf-rxprocs-rxcompleterequest_real.md) | RxCompleteRequest_Real completes the IRP request associated with an RX_CONTEXT structure. |
| [RxDereference function](nf-rxprocs-rxdereference.md) | RxDereference decrements the NodeReferenceCount member of a structure by one for several reference counted data structures used by RDBSS. |
| [RxDriverEntry function](nf-rxprocs-rxdriverentry.md) | RxDriverEntry is called by a monolithic network mini-redirector driver from its DriverEntry routine to initialize the RDBSS static library. |
| [RxFinalizeConnection function](nf-rxprocs-rxfinalizeconnection.md) | RxFinalizeConnection deletes a connection to a share. |
| [RxFinalizeNetFcb function](nf-rxprocs-rxfinalizenetfcb.md) | RxFinalizeNetFCB finalizes the given FCB structure. The caller must have an exclusive lock on the NET_ROOT associated with FCB. |
| [RxForceFinalizeAllVNetRoots function](nf-rxprocs-rxforcefinalizeallvnetroots.md) | RxForceFinalizeAllVNetRoots force finalizes all the V_NET_ROOT structures associated with a given NET_ROOT structure. The caller must have an exclusive lock on the netname table associated with the device object. |
| [RxFsdPostRequest function](nf-rxprocs-rxfsdpostrequest.md) | RxFsdPostRequest queues the I/O request packet (IRP) specified by an RX_CONTEXT structure to the worker queue for processing by the file system process (FSP). |
| [RxIndicateChangeOfBufferingState function](nf-rxprocs-rxindicatechangeofbufferingstate.md) | RxIndicateChangeOfBufferingState is called to register a change buffering state request (an oplock break indication, for example) for later processing. If necessary, worker thread routines for further processing are activated. |
| [RxIndicateChangeOfBufferingStateForSrvOpen function](nf-rxprocs-rxindicatechangeofbufferingstateforsrvopen.md) | RxIndicateChangeOfBufferingStateForSrvOpen is called to register a change buffering state request (an oplock break indication, for example) for later processing. If the necessary preconditions are satisfied, the oplock is processed further. |
| [RxIsThisACscAgentOpen function](nf-rxprocs-rxisthisacscagentopen.md) | RxIsThisACscAgentOpen determines if a file open was made by a user-mode client-side caching agent. |
| [RxLockEnumerator function](nf-rxprocs-rxlockenumerator.md) | RxLockEnumerator is called from a network mini-redirector to enumerate the file locks on an FCB. |
| [RxLogEventDirect function](nf-rxprocs-rxlogeventdirect.md) | RxLogEventDirect is called to log an error to the I/O error log. It is recommended that the RXLogEvent macro or the RxLogFailure macro be used instead of calling this routine directly. |
| [RxLogEventWithAnnotation function](nf-rxprocs-rxlogeventwithannotation.md) | RxLogEventWithAnnotation allocates an I/O error log structure, fills it in with information, and writes the entry to the I/O error log. |
| [RxLogEventWithBufferDirect function](nf-rxprocs-rxlogeventwithbufferdirect.md) | RxLogEventWithBufferDirect allocates an I/O error log structure, fills it in with information, and writes the entry to the I/O error log. |
| [RxMapSystemBuffer function](nf-rxprocs-rxmapsystembuffer.md) | RxMapSystemBuffer returns the system buffer address from the IRP. |
| [RxPrepareToReparseSymbolicLink function](nf-rxprocs-rxpreparetoreparsesymboliclink.md) | RxPrepareToReparseSymbolicLink sets up the file object name to facilitate a reparse. This routine is used by the network mini-redirectors to traverse symbolic links. |
| [RxPurgeAllFobxs function](nf-rxprocs-rxpurgeallfobxs.md) | RxPurgeAllFobxs purges all of the FOBX structures associated with a network mini-redirector. |
| [RxReference function](nf-rxprocs-rxreference.md) | RxReference increments the NodeReferenceCount member of a structure by one for several of the reference counted data structures used by RDBSS. |
| [RxScavengeAllFobxs function](nf-rxprocs-rxscavengeallfobxs.md) | RxScavengeAllFobxs scavenges all of the FOBX structures associated with a network mini-redirector device object. |
| [RxSetSrvCallDomainName function](nf-rxprocs-rxsetsrvcalldomainname.md) | RxSetSrvCallDomainName is called by a network mini-redirector driver to set the domain name associated with any given server (SRV_CALL structure). |

## Macros

| Title   | Description   |
| ---- |:---- |
| [FsRtlCheckOplock macro](nf-rxprocs-fsrtlcheckoplock.md) | The FsRtlCheckOplock routine synchronizes the IRP for a file I/O operation with the file's current opportunistic lock (oplock) state. |
| [FsRtlNotifyFullChangeDirectory macro](nf-rxprocs-fsrtlnotifyfullchangedirectory.md) | The FsRtlNotifyFullChangeDirectory routine creates a notify structure for a notification request and adds it to the specified notify list. |
| [FsRtlOplockIsFastIoPossible macro](nf-rxprocs-fsrtloplockisfastiopossible.md) | FsRtlOplockIsFastIoPossible checks a file's opportunistic lock (oplock) state to determine whether fast I/O can be performed on the file. |
