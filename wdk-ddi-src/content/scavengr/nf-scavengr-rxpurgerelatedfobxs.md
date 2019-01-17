---
UID: NF:scavengr.RxPurgeRelatedFobxs
title: RxPurgeRelatedFobxs function
description: RxPurgeRelatedFobxs purges all of the FOBX structures associated with a NET_ROOT structure.
old-location: ifsk\rxpurgerelatedfobxs.htm
tech.root: ifsk
ms.assetid: bb2d56a0-37f4-48bc-8b56-e5250f0f7443
ms.date: 04/16/2018
ms.keywords: RxPurgeRelatedFobxs, RxPurgeRelatedFobxs function [Installable File System Drivers], ifsk.rxpurgerelatedfobxs, rxref_56862045-c344-4392-9a25-b4e22c36379f.xml, scavengr/RxPurgeRelatedFobxs
ms.topic: function
req.header: scavengr.h
req.include-header: Rxprocs.h
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
-	scavengr.h
api_name:
-	RxPurgeRelatedFobxs
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxPurgeRelatedFobxs function


## -description


<b>RxPurgeRelatedFobxs</b> purges all of the FOBX structures associated with a NET_ROOT structure.


## -parameters




### -param NetRoot

A pointer to the NET_ROOT structure for which the FOBX structures need to be purged.


### -param RxContext

A pointer to the RX_CONTEXT structure.


### -param AttemptFinalization

<p>A Boolean value that indicates whether an attempt to finalize and release the associated FCB structure should occur.</p>


### -param PurgingFcb

A pointer to the FCB structure for which purging should occur.


## -returns



<b>RxPurgeRelatedFobxs</b> returns STATUS_SUCCESS on success or one of the following error values on failure: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
No related FOBX structures could be purged.

</td>
</tr>
</table>
 




## -remarks



At cleanup there are no more user handles associated with the file object. In such cases, the time window between close and cleanup is dictated by the additional references maintained by the memory manager and cache manager. On cleanup, the FOBX is put on a close pending list and removed from the corresponding list when a close operation is received. In the interim, if an open operation is failing with ACCESS_DENIED status, then RDBSS can force a purge of the FOBX structure. This is a synchronous operation.

For directory renames, all files under the directory need to be closed. A network mini-redirector might call <b>RxPurgeRelatedFobxs</b> and <b>RxScavengeFobxsForNetRoot</b> in response to an IRP_MJ_SET_INFORMATION request to rename a directory. By passing in the NET_ROOT structure for the directory and a <b>NULL</b> FCB, all of the FOBX structures associated with the directory would be purged and scavenged.

The <b>RxPurgeRelatedFobxs</b> routine attempts to purge all of the FOBX structures that had a close operation pending before the purge request was received. The <b>RxPurgeRelatedFobxs</b> routine acquires the scavenger mutex, traverses the <b>ClosePendingFobxsList</b> member on the scavenger object removing list entries, and then releases the mutex. 

If <i>AttemptFinalize</i> is set to <b>TRUE</b>, then <b>RxPurgeRelatedFobxs</b> will try to finalize and release the associated FCB.

If <i>PFCB</i> is not <b>NULL</b>, and this purging FCB strcuture is not the same as the FCB structure associated with the FOBX on the <b>ClosePendingFobxsList</b> member, then <b>RxPurgeRelatedFobxs</b> will call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549838">MRxAreFilesAliased</a> callback routine provided by the network mini-redirector if this routine is supported. The call to <b>MRxAreFilesAliased</b> is to determine if the PFCB is an alias for the FCB associated with the FOBX structure. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549838">MRxAreFilesAliased</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554673">RxPurgeAllFobxs</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554707">RxScavengeAllFobxs</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554713">RxScavengeFobxsForNetRoot</a>
 

 

