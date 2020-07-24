---
UID: NF:rxprocs.RxScavengeAllFobxs
title: RxScavengeAllFobxs function (rxprocs.h)
description: RxScavengeAllFobxs scavenges all of the FOBX structures associated with a network mini-redirector device object.
old-location: ifsk\rxscavengeallfobxs.htm
tech.root: ifsk
ms.assetid: dd849f18-6271-483a-9c00-b7fe50109989
ms.date: 04/16/2018
keywords: ["RxScavengeAllFobxs function"]
ms.keywords: RxScavengeAllFobxs, RxScavengeAllFobxs function [Installable File System Drivers], ifsk.rxscavengeallfobxs, rxprocs/RxScavengeAllFobxs, rxref_d983b334-0cc7-42ab-abc7-79f1bc0876cd.xml
f1_keywords:
 - "rxprocs/RxScavengeAllFobxs"
 - "RxScavengeAllFobxs"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- rxprocs.h
api_name:
- RxScavengeAllFobxs
targetos: Windows
req.typenames: 
---

# RxScavengeAllFobxs function


## -description


<b>RxScavengeAllFobxs</b> scavenges all of the FOBX structures associated with a network mini-redirector device object.


## -parameters




### -param RxDeviceObject

A pointer to the mini-redirector device object for which the scavenge should be done.


## -remarks



At cleanup, there are no more user handles associated with the file object. In such cases, the time window between close and cleanup is dictated by the additional references maintained by the memory manager and cache manager. RDBSS uses a scavenger process running on a separate thread to scavenge and purge unneeded FOBX and other structures.

A network mini-redirectors might call <b>RxPurgeAllFobxs</b> and <b>RxScavengeAllFobsx</b> in response to a PnP power change event. 

The <b>RxScavengeAllFobxs</b> routine acquires the scavenger mutex, traverses the <b>FobxFinalizationList</b> member on the scavenger object, and inserts any entries found at the tail of the <b>ScavengerFinalizationList </b>member, and then releases the scavenger mutex. 

On checked builds, <b>RxScavengeAllFobxs</b> causes the system to ASSERT for the following condition:

<ul>
<li>
The <b>NodeTypeCode</b> member of an FOBX structure is not RDBSS_NTC_FOBX.

</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxpurgeallfobxs">RxPurgeAllFobxs</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scavengr/nf-scavengr-rxpurgerelatedfobxs">RxPurgeRelatedFobxs</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scavengr/nf-scavengr-rxscavengefobxsfornetroot">RxScavengeFobxsForNetRoot</a>
 

 

