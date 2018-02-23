---
UID: NF:rxprocs.RxScavengeAllFobxs
title: RxScavengeAllFobxs function
author: windows-driver-content
description: RxScavengeAllFobxs scavenges all of the FOBX structures associated with a network mini-redirector device object.
old-location: ifsk\rxscavengeallfobxs.htm
old-project: ifsk
ms.assetid: dd849f18-6271-483a-9c00-b7fe50109989
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ifsk.rxscavengeallfobxs, rxprocs/RxScavengeAllFobxs, rxref_d983b334-0cc7-42ab-abc7-79f1bc0876cd.xml, RxScavengeAllFobxs function [Installable File System Drivers], RxScavengeAllFobxs
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
-	RxScavengeAllFobxs
product: Windows
targetos: Windows
req.typenames: RX_CONTEXT, *PRX_CONTEXT
req.product: Windows 10 or later.
---

# RxScavengeAllFobxs function


## -description


<b>RxScavengeAllFobxs</b> scavenges all of the FOBX structures associated with a network mini-redirector device object.


## -syntax


````
VOID RxScavengeAllFobxs(
   PRDBSS_DEVICE_OBJECT RxDeviceObject
);
````


## -parameters




### -param RxDeviceObject

A pointer to the mini-redirector device object for which the scavenge should be done.


## -returns



None 




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

<a href="..\scavengr\nf-scavengr-rxpurgerelatedfobxs.md">RxPurgeRelatedFobxs</a>



<a href="..\rxprocs\nf-rxprocs-rxpurgeallfobxs.md">RxPurgeAllFobxs</a>



<a href="..\scavengr\nf-scavengr-rxscavengefobxsfornetroot.md">RxScavengeFobxsForNetRoot</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxScavengeAllFobxs function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

