---
UID: NF:scavengr.RxPurgeRelatedFobxs
title: RxPurgeRelatedFobxs function
author: windows-driver-content
description: RxPurgeRelatedFobxs purges all of the FOBX structures associated with a NET_ROOT structure.
old-location: ifsk\rxpurgerelatedfobxs.htm
old-project: ifsk
ms.assetid: bb2d56a0-37f4-48bc-8b56-e5250f0f7443
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RxPurgeRelatedFobxs
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: scavengr.h
req.include-header: Rxprocs.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RxPurgeRelatedFobxs
req.alt-loc: scavengr.h
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
req.typenames: RX_CONTEXT, *PRX_CONTEXT
req.product: Windows 10 or later.
---

# RxPurgeRelatedFobxs function



## -description
<b>RxPurgeRelatedFobxs</b> purges all of the FOBX structures associated with a NET_ROOT structure.



## -syntax

````
NTSTATUS RxPurgeRelatedFobxs(
   PNET_ROOT   NetRoot,
   PRX_CONTEXT RxContext,
   BOOLEAN     AttemptFinalize,
   PFCB        PurgingFcb
);
````


## -parameters

### -param NetRoot 

A pointer to the NET_ROOT structure for which the FOBX structures need to be purged.


### -param RxContext 

A pointer to the RX_CONTEXT structure.


### -param AttemptFinalize 

A Boolean value that indicates whether an attempt to finalize and release the associated FCB structure should occur.


### -param PurgingFcb 

A pointer to the FCB structure for which purging should occur.


## -returns
<b>RxPurgeRelatedFobxs</b> returns STATUS_SUCCESS on success or one of the following error values on failure: 
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>No related FOBX structures could be purged.

 


## -remarks
At cleanup there are no more user handles associated with the file object. In such cases, the time window between close and cleanup is dictated by the additional references maintained by the memory manager and cache manager. On cleanup, the FOBX is put on a close pending list and removed from the corresponding list when a close operation is received. In the interim, if an open operation is failing with ACCESS_DENIED status, then RDBSS can force a purge of the FOBX structure. This is a synchronous operation.

For directory renames, all files under the directory need to be closed. A network mini-redirector might call <b>RxPurgeRelatedFobxs</b> and <b>RxScavengeFobxsForNetRoot</b> in response to an IRP_MJ_SET_INFORMATION request to rename a directory. By passing in the NET_ROOT structure for the directory and a <b>NULL</b> FCB, all of the FOBX structures associated with the directory would be purged and scavenged.

The <b>RxPurgeRelatedFobxs</b> routine attempts to purge all of the FOBX structures that had a close operation pending before the purge request was received. The <b>RxPurgeRelatedFobxs</b> routine acquires the scavenger mutex, traverses the <b>ClosePendingFobxsList</b> member on the scavenger object removing list entries, and then releases the mutex. 

If <i>AttemptFinalize</i> is set to <b>TRUE</b>, then <b>RxPurgeRelatedFobxs</b> will try to finalize and release the associated FCB.

If <i>PFCB</i> is not <b>NULL</b>, and this purging FCB strcuture is not the same as the FCB structure associated with the FOBX on the <b>ClosePendingFobxsList</b> member, then <b>RxPurgeRelatedFobxs</b> will call the <a href="..\mrx\nc-mrx-pmrx_chkfcb_calldown.md">MRxAreFilesAliased</a> callback routine provided by the network mini-redirector if this routine is supported. The call to <b>MRxAreFilesAliased</b> is to determine if the PFCB is an alias for the FCB associated with the FOBX structure. 


## -see-also
<dl>
<dt>
<a href="..\mrx\nc-mrx-pmrx_chkfcb_calldown.md">MRxAreFilesAliased</a>
</dt>
<dt>
<a href="..\rxprocs\nf-rxprocs-rxpurgeallfobxs.md">RxPurgeAllFobxs</a>
</dt>
<dt>
<a href="..\rxprocs\nf-rxprocs-rxscavengeallfobxs.md">RxScavengeAllFobxs</a>
</dt>
<dt>
<a href="..\scavengr\nf-scavengr-rxscavengefobxsfornetroot.md">RxScavengeFobxsForNetRoot</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxPurgeRelatedFobxs function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

