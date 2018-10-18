---
UID: NF:ntddk.RtlSubtreeSuccessor
title: RtlSubtreeSuccessor function
author: windows-driver-content
description: The RtlSubtreeSuccessor routine returns a pointer to the successor of the specified node within the subtree that is rooted at that node.
old-location: ifsk\rtlsubtreesuccessor.htm
tech.root: ifsk
ms.assetid: de592c2a-6f52-48ef-b2ee-253d83cafa80
ms.date: 4/16/2018
ms.keywords: RtlSubtreeSuccessor, RtlSubtreeSuccessor routine [Installable File System Drivers], ifsk.rtlsubtreesuccessor, ntddk/RtlSubtreeSuccessor, rtlref_65e50284-427f-47d9-92c7-719b8bc1bab5.xml
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
-	RtlSubtreeSuccessor
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlSubtreeSuccessor function


## -description


The <b>RtlSubtreeSuccessor</b> routine returns a pointer to the successor of the specified node within the subtree that is rooted at that node. 


## -parameters




### -param Links [in]

A pointer to the node. The node must have been initialized by calling <b>RtlInitializeSplayLinks</b>. 


## -returns



<b>RtlSubtreeSuccessor</b> returns a pointer to the subtree successor of the node at <i>Links</i>, or <b>NULL</b> if the given node has no subtree successor. 




## -remarks



If the node at <i>Links</i> has a right subtree, the leftmost node of that subtree is the subtree successor. 

Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlSubtreeSuccessor</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the tree is nonpaged. If the tree is paged, callers must be running at IRQL &lt; DISPATCH_LEVEL. Usually callers are running at IRQL PASSIVE_LEVEL. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553010">RtlInitializeSplayLinks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553188">RtlRealSuccessor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553226">RtlSplay</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553237">RtlSubtreePredecessor</a>
 

 

