---
UID: NF:rxprocs.RxPurgeAllFobxs
title: RxPurgeAllFobxs function (rxprocs.h)
description: RxPurgeAllFobxs purges all of the FOBX structures associated with a network mini-redirector.
old-location: ifsk\rxpurgeallfobxs.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["RxPurgeAllFobxs function"]
ms.keywords: RxPurgeAllFobxs, RxPurgeAllFobxs function [Installable File System Drivers], ifsk.rxpurgeallfobxs, rxprocs/RxPurgeAllFobxs, rxref_80dc8a6f-2b11-44b1-986b-b29402e4d46e.xml
req.header: rxprocs.h
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RxPurgeAllFobxs
 - rxprocs/RxPurgeAllFobxs
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rxprocs.h
api_name:
 - RxPurgeAllFobxs
---

# RxPurgeAllFobxs function


## -description

<b>RxPurgeAllFobxs</b> purges all of the FOBX structures associated with a network mini-redirector.

## -parameters

### -param RxDeviceObject

A pointer to the mini-redirector device object for which the purge should be done.

## -remarks

At cleanup, there are no more user handles associated with the file object. In such cases, the time window between close and cleanup is dictated by the additional references maintained by memory manager and cache manager. RDBSS uses a scavenger process running on a separate thread to scavenge and purge unneeded FOBX and other structures.

A network mini-redirector might call <b>RxPurgeAllFobxs</b> and <b>RxScavengeAllFobsx</b> in response to a PnP power change event. 

The <b>RxPurgeAllFobxs</b> routine acquires the scavenger mutex, traverses the <b>ClosePendingFobxsList</b> member on the scavenger object removing list entries, and then releases the mutex. If the FOBX structure is not <b>NULL</b>,  <b>RxPurgeAllFobxs</b> will purge the FOBX structure and try to acquire an exclusive lock on the associated FCB structure. If successful, <b>RxPurgeAllFobxs</b> will then try to dereference the NET_FOBX structure and dereference, finalize, and release the FCB structure.

On checked builds, <b>RxPurgeAllFobxs</b> causes the system to ASSERT for a number of conditions including the following:

<ul>
<li>
The <b>Flink</b> member of <i>RxScavenger->ClosePendingFobxsList</i> structure on the <b>RxDeviceObject</b> is <b>NULL</b>.

</li>
<li>
<i>Fobx->NodeTypeCode</i> is not RDBSS_NTC_FOBX.

</li>
<li>
The <b>Flink</b> and <b>Blink</b> members for a list entry are <b>NULL</b>.

</li>
</ul>

## -see-also

<a href="/windows-hardware/drivers/ddi/scavengr/nf-scavengr-rxpurgerelatedfobxs">RxPurgeRelatedFobxs</a>



<a href="/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxscavengeallfobxs">RxScavengeAllFobxs</a>



<a href="/windows-hardware/drivers/ddi/scavengr/nf-scavengr-rxscavengefobxsfornetroot">RxScavengeFobxsForNetRoot</a>
