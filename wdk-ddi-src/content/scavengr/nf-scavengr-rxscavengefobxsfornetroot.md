---
UID: NF:scavengr.RxScavengeFobxsForNetRoot
title: RxScavengeFobxsForNetRoot function
author: windows-driver-content
description: RxScavengeFobxsForNetRoot scavenges all of the FOBX structures associated with a given NET_ROOT structure.
old-location: ifsk\rxscavengefobxsfornetroot.htm
old-project: ifsk
ms.assetid: 2a2320e6-b114-4ea7-9f2f-27fd47fef770
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: scavengr/RxScavengeFobxsForNetRoot, RxScavengeFobxsForNetRoot, ifsk.rxscavengefobxsfornetroot, RxScavengeFobxsForNetRoot function [Installable File System Drivers], rxref_9fac9a87-f068-4ee4-909c-85a41c9884d6.xml
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
-	scavengr.h
apiname:
-	RxScavengeFobxsForNetRoot
product: Windows
targetos: Windows
req.typenames: RX_CONTEXT, *PRX_CONTEXT
req.product: Windows 10 or later.
---

# RxScavengeFobxsForNetRoot function


## -description


<b>RxScavengeFobxsForNetRoot</b> scavenges all of the FOBX structures associated with a given NET_ROOT structure.


## -syntax


````
VOID RxScavengeFobxsForNetRoot(
   PNET_ROOT NetRoot,
   PFCB      PurgingFcb
);
````


## -parameters




### -param NetRoot

A pointer to the NET_ROOT structure for which the FOBX structures need to be scavenged.


### -param PurgingFcb

A pointer to the FCB for which the scavenging should occur.


### -param SynchronizeWithScavenger

TBD




## -returns



None 




## -remarks



At cleanup, there are no more user handles associated with the file object. In such cases, the time window between close and cleanup is dictated by the additional references maintained by the memory manager and cache manager. On cleanup, the FOBX is put on a close pending list and removed from the corresponding list when a close operation is received. In the interim, if an open operation is failing with ACCESS_DENIED status, then RDBSS can force a purge and scavenge of the FOBX structure. This is a synchronous operation.

For directory renames, all files under the directory need to be closed. So, a network mini-redirector might call <b>RxPurgeRelatedFobxs</b> and <b>RxScavengeFobxsForNetRoot</b> in response to a IRP_MJ_SET_INFORMATION request to rename a directory. By passing in the NET_ROOT structure for the directory and a <b>NULL</b> FCB, all of the FOBX structures associated with the directory would be purged and scavenged.

The <b>RxScavengeFobxsForNetRoot</b> routine acquires the scavenger mutex, traverses the <b>FobxsToBeFinalized</b> list member of the scavenger object and adds any entries found to tail of the <b>ScavengerFinalizationList</b> member of the scavenger object, and then releases the mutex. 

If <i>PurgingFcb </i>is not <b>NULL</b>, and this purging FCB structure is not the same as the FCB associated with the FOBX structure on the <b>FobxsToBeFinalized</b> list member of the scavenger object, <b>RxScavengeFobxsForNetRoot</b> will call the <a href="..\mrx\nc-mrx-pmrx_chkfcb_calldown.md">MRxAreFilesAliased</a> callback routine provided by the network mini-redirector if it is supported. The call to <b>MRxAreFilesAliased</b> is to determine if the PFCB is an alias for the FCB associated with the FOBX structure.

On checked builds, <b>RxScavengeAllFobxs</b> causes the system to ASSERT for the following condition:

<ul>
<li>
The <b>NodeTypeCode</b> member of an FOBX structure is not RDBSS_NTC_FOBX.

</li>
</ul>



## -see-also

<a href="..\rxprocs\nf-rxprocs-rxscavengeallfobxs.md">RxScavengeAllFobxs</a>



<a href="..\mrx\nc-mrx-pmrx_chkfcb_calldown.md">MRxAreFilesAliased</a>



<a href="..\scavengr\nf-scavengr-rxpurgerelatedfobxs.md">RxPurgeRelatedFobxs</a>



<a href="..\rxprocs\nf-rxprocs-rxpurgeallfobxs.md">RxPurgeAllFobxs</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxScavengeFobxsForNetRoot function%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

