---
UID: NF:rxprocs.RxPurgeAllFobxs
title: RxPurgeAllFobxs function
author: windows-driver-content
description: RxPurgeAllFobxs purges all of the FOBX structures associated with a network mini-redirector.
old-location: ifsk\rxpurgeallfobxs.htm
old-project: ifsk
ms.assetid: 3d2a31be-1b59-48a8-8cde-61d7f7319724
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: rxprocs/RxPurgeAllFobxs, RxPurgeAllFobxs function [Installable File System Drivers], rxref_80dc8a6f-2b11-44b1-986b-b29402e4d46e.xml, ifsk.rxpurgeallfobxs, RxPurgeAllFobxs
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rxprocs.h
apiname:
-	RxPurgeAllFobxs
product: Windows
targetos: Windows
req.typenames: RX_CONTEXT, *PRX_CONTEXT
req.product: Windows 10 or later.
---

# RxPurgeAllFobxs function


## -description


<b>RxPurgeAllFobxs</b> purges all of the FOBX structures associated with a network mini-redirector. 


## -syntax


````
VOID RxPurgeAllFobxs(
   PRDBSS_DEVICE_OBJECT RxDeviceObject
);
````


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

<a href="..\rxprocs\nf-rxprocs-rxscavengeallfobxs.md">RxScavengeAllFobxs</a>



<a href="..\scavengr\nf-scavengr-rxpurgerelatedfobxs.md">RxPurgeRelatedFobxs</a>



<a href="..\scavengr\nf-scavengr-rxscavengefobxsfornetroot.md">RxScavengeFobxsForNetRoot</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxPurgeAllFobxs function%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

