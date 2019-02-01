---
UID: NF:rxprocs.RxPurgeAllFobxs
title: RxPurgeAllFobxs function (rxprocs.h)
description: RxPurgeAllFobxs purges all of the FOBX structures associated with a network mini-redirector.
old-location: ifsk\rxpurgeallfobxs.htm
tech.root: ifsk
ms.assetid: 3d2a31be-1b59-48a8-8cde-61d7f7319724
ms.date: 04/16/2018
ms.keywords: RxPurgeAllFobxs, RxPurgeAllFobxs function [Installable File System Drivers], ifsk.rxpurgeallfobxs, rxprocs/RxPurgeAllFobxs, rxref_80dc8a6f-2b11-44b1-986b-b29402e4d46e.xml
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rxprocs.h
api_name:
-	RxPurgeAllFobxs
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxPurgeAllFobxs function


## -description


<b>RxPurgeAllFobxs</b> purges all of the FOBX structures associated with a network mini-redirector. 


## -parameters




### -param RxDeviceObject

A pointer to the mini-redirector device object for which the purge should be done.


## -returns



None 




## -remarks



At cleanup, there are no more user handles associated with the file object. In such cases, the time window between close and cleanup is dictated by the additional references maintained by memory manager and cache manager. RDBSS uses a scavenger process running on a separate thread to scavenge and purge unneeded FOBX and other structures.

A network mini-redirector might call <b>RxPurgeAllFobxs</b> and <b>RxScavengeAllFobsx</b> in response to a PnP power change event. 

The <b>RxPurgeAllFobxs</b> routine acquires the scavenger mutex, traverses the <b>ClosePendingFobxsList</b> member on the scavenger object removing list entries, and then releases the mutex. If the FOBX structure is not <b>NULL</b>,  <b>RxPurgeAllFobxs</b> will purge the FOBX structure and try to acquire an exclusive lock on the associated FCB structure. If successful, <b>RxPurgeAllFobxs</b> will then try to dereference the NET_FOBX structure and dereference, finalize, and release the FCB structure.

On checked builds, <b>RxPurgeAllFobxs</b> causes the system to ASSERT for a number of conditions including the following:

<ul>
<li>
The <b>Flink</b> member of <i>RxScavenger-&gt;ClosePendingFobxsList</i> structure on the <b>RxDeviceObject</b> is <b>NULL</b>.

</li>
<li>
<i>Fobx-&gt;NodeTypeCode</i> is not RDBSS_NTC_FOBX.

</li>
<li>
The <b>Flink</b> and <b>Blink</b> members for a list entry are <b>NULL</b>.

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554679">RxPurgeRelatedFobxs</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554707">RxScavengeAllFobxs</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554713">RxScavengeFobxsForNetRoot</a>
 

 

