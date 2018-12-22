---
UID: NF:ntddk.RtlRealSuccessor
title: RtlRealSuccessor function
description: The RtlRealSuccessor routine returns a pointer to the successor of the specified node in the splay link tree.
old-location: ifsk\rtlrealsuccessor.htm
tech.root: ifsk
ms.assetid: 19180ab8-7ac6-45cb-8f17-b16368bbb32b
ms.date: 04/16/2018
ms.keywords: RtlRealSuccessor, RtlRealSuccessor routine [Installable File System Drivers], ifsk.rtlrealsuccessor, ntddk/RtlRealSuccessor, rtlref_5bf190a8-a1c9-45d8-8be3-73178d2f7add.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlRealSuccessor
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlRealSuccessor function


## -description


The <b>RtlRealSuccessor</b> routine returns a pointer to the successor of the specified node in the splay link tree. 


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553186">RtlRealPredecessor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553226">RtlSplay</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553239">RtlSubtreeSuccessor</a>
 

 

