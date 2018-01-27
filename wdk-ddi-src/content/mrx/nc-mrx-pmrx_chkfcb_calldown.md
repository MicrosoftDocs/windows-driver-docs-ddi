---
UID: NC:mrx.PMRX_CHKFCB_CALLDOWN
title: PMRX_CHKFCB_CALLDOWN
author: windows-driver-content
description: The MRxAreFilesAliased routine is called by RDBSS to request the network mini-redirector to determine if two FCB structures represent the same file.
old-location: ifsk\mrxarefilesaliased.htm
old-project: ifsk
ms.assetid: 273266b3-98f4-4c93-a06b-8e149440ad24
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.mrxarefilesaliased, MRxAreFilesAliased, MRxAreFilesAliased routine [Installable File System Drivers], MRxAreFilesAliased, PMRX_CHKFCB_CALLDOWN, PMRX_CHKFCB_CALLDOWN, mrx/MRxAreFilesAliased, mrxref_5d6e6988-84d7-43ac-860e-4f184686a9e6.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: mrx.h
req.include-header: Mrx.h
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
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	mrx.h
apiname: 
-	MRxAreFilesAliased
product: Windows
targetos: Windows
req.typenames: SetDSMCounters_IN, *PSetDSMCounters_IN
---

# PMRX_CHKFCB_CALLDOWN callback


## -description


The<b> MRxAreFilesAliased</b> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request the network mini-redirector to determine if two FCB structures represent the same file. 


## -prototype


````
PMRX_CHKFCB_CALLDOWN MRxAreFilesAliased;

NTSTATUS MRxAreFilesAliased(
  _In_ PFCB Fcb1,
  _In_ PFCB Fcb2
)
{ ... }
````


## -parameters




### -param Fcb1 [in]

A pointer to the first FCB structure. 


### -param Fcb2 [in]

A pointer to the second FCB structure.


## -returns


<b>MRxAreFilesAliased</b> returns STATUS_SUCCESS indicating that the files are not aliased, or an appropriate NTSTATUS value, such as the following: 
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_MORE_PROCESSING_REQUIRED</b></dt>
</dl>
</td>
<td width="60%">
The <b>IndexNumber.QuadPart</b> members of the two FCB structures are identical. This value indicates that the two files that are being compared are aliases.

</td>
</tr>
</table> 



## -remarks


RDBSS calls this routine when processing two files that appear to be the same but have different names (for example, an MS-DOS short name and a long name).

<b>MRxAreFilesAliased</b> is called by the <a href="..\scavengr\nf-scavengr-rxpurgerelatedfobxs.md">RxPurgeRelatedFobxs</a> routine when purging all the structures of an FOBX structure associated with a NET_ROOT structure. As part of this process, an attempt is made to purge all the FOBX structures that had a close pending before the purge request was received. RDBSS needs to scavenge any temporary FOBX structures in the following cases: 
<ol>
<li>
The <i>PurgingFcb</i> parameter that is passed to the <a href="..\scavengr\nf-scavengr-rxpurgerelatedfobxs.md">RxPurgeRelatedFobxs</a> routine is the FCB structure for which the scavenging should occur. When this parameter is a directory, RDBSS needs to ensure that files that can potentially be in that directory are closed.

</li>
<li>
The FCB structure that is associated with the FOBX structure on the <b>FobxsToBeFinalized</b> member of the RDBSS_SCAVENGER structure doesn't point to the same FCB structure as the <i>PurgingFCB</i> parameter passed to <a href="..\scavengr\nf-scavengr-rxpurgerelatedfobxs.md">RxPurgeRelatedFobxs</a>. This is complicated by the fact that they might not be the same FCB structures, but are actually the same file because of aliasing. In this case, the <b>MRxAreFilesAliased</b> routine is called to determine if the FCB structure is aliased.

</li>
</ol><b>MRxAreFilesAliased</b> is also called by the <a href="..\scavengr\nf-scavengr-rxscavengefobxsfornetroot.md">RxScavengeFobxsForNetRoot</a> routine when purging all the file objects associated with a NET_ROOT structure. This is complicated by the fact that the <i>PurgingFCB</i> parameter passed to <b>RxScavengeFobxsForNetRoot</b> and the FCB structure that is associated with the NET_ROOT structure might actually be the same file because of aliasing. In this case, the <b>MRxAreFilesAliased</b> routine is called to determine if the FCB structure is aliased.  



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550839">MRxTruncate</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550669">MRxFlush</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549878">MRxExtendForCache</a>

<a href="..\scavengr\nf-scavengr-rxpurgerelatedfobxs.md">RxPurgeRelatedFobxs</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549862">MRxCreate</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550691">MRxIsLockRealizable</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549871">MRxDeallocateForFcb</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550844">MRxZeroExtend</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550817">MRxShouldTryToCollapseThisOpen</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549847">MRxCollapseOpen</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550677">MRxForceClosed</a>

<a href="..\mrx\nc-mrx-pmrx_calldown.md">MRxCloseSrvOpen</a>

<a href="..\scavengr\nf-scavengr-rxscavengefobxsfornetroot.md">RxScavengeFobxsForNetRoot</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549879">MRxExtendForNonCache</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549841">MRxCleanupFobx</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549872">MRxDeallocateForFobx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PMRX_CHKFCB_CALLDOWN routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

