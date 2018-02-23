---
UID: NF:ntddk.RtlRealSuccessor
title: RtlRealSuccessor function
author: windows-driver-content
description: The RtlRealSuccessor routine returns a pointer to the successor of the specified node in the splay link tree.
old-location: ifsk\rtlrealsuccessor.htm
old-project: ifsk
ms.assetid: 19180ab8-7ac6-45cb-8f17-b16368bbb32b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: rtlref_5bf190a8-a1c9-45d8-8be3-73178d2f7add.xml, ifsk.rtlrealsuccessor, ntddk/RtlRealSuccessor, RtlRealSuccessor, RtlRealSuccessor routine [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: See Remarks section.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlRealSuccessor
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# RtlRealSuccessor function


## -description


The <b>RtlRealSuccessor</b> routine returns a pointer to the successor of the specified node in the splay link tree. 


## -syntax


````
PRTL_SPLAY_LINKS RtlRealSuccessor(
  _In_ PRTL_SPLAY_LINKS Links
);
````


## -parameters




### -param Links [in]

Pointer to the node. The node must have been initialized by calling <b>RtlInitializeSplayLinks</b>. 


## -returns



<b>RtlRealSuccessor</b> returns a pointer to the successor of the node at <i>Links</i>, or <b>NULL</b> if the node has no successor. 




## -remarks



The real successor of a given node is determined as follows:

<ul>
<li>
If the given node has a right subtree, the leftmost node in the right subtree of the node at <i>Links</i> is the successor. Note that <b>RtlSubtreeSuccessor</b> returns the same result for this case. 

</li>
<li>
Otherwise, the nearest ancestor node, of which the given node is a left-subtree descendant, is the successor. 

</li>
</ul>
Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlRealSuccessor</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the tree is nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL. 




## -see-also

<a href="..\ntddk\nf-ntddk-rtlsubtreesuccessor.md">RtlSubtreeSuccessor</a>



<a href="..\ntddk\nf-ntddk-rtlsplay.md">RtlSplay</a>



<a href="..\ntddk\nf-ntddk-rtlrealpredecessor.md">RtlRealPredecessor</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlRealSuccessor routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

