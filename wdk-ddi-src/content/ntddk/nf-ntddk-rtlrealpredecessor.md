---
UID: NF:ntddk.RtlRealPredecessor
title: RtlRealPredecessor function (ntddk.h)
description: The RtlRealPredecessor routine returns a pointer to the predecessor of the specified node in the splay link tree.
old-location: ifsk\rtlrealpredecessor.htm
tech.root: ifsk
ms.assetid: 8cb981a4-7dea-4d42-bbde-35cf5494494b
ms.date: 04/16/2018
keywords: ["RtlRealPredecessor function"]
ms.keywords: RtlRealPredecessor, RtlRealPredecessor routine [Installable File System Drivers], ifsk.rtlrealpredecessor, ntddk/RtlRealPredecessor, rtlref_1c872dd0-50cb-48ff-a7e4-e3c88b3b087f.xml
f1_keywords:
 - "ntddk/RtlRealPredecessor"
 - "RtlRealPredecessor"
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlRealPredecessor
targetos: Windows
req.typenames: 
---

# RtlRealPredecessor function


## -description


The <b>RtlRealPredecessor</b> routine returns a pointer to the predecessor of the specified node in the splay link tree. 


## -parameters




### -param Links [in]

Pointer to the node. The node must have been initialized by calling <b>RtlInitializeSplayLinks</b>. 


## -returns



<b>RtlRealPredecessor</b> returns a pointer to the predecessor of the node at <i>Links</i>, or <b>NULL</b> if the node has no predecessor. 




## -remarks



The predecessor of a given node is determined as follows:

<ul>
<li>
If the given node has a left subtree, the rightmost node in the left subtree of the node at <i>Links</i> is the predecessor. Note that <b>RtlSubtreePredecessor</b> returns the same result for this case. 

</li>
<li>
Otherwise, the nearest ancestor node, of which the given node is a right-subtree descendant, is the predecessor. 

</li>
</ul>
Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlRealPredecessor</b> must be running at IRQL <= DISPATCH_LEVEL if the tree is nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlrealsuccessor">RtlRealSuccessor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlsplay">RtlSplay</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlsubtreepredecessor">RtlSubtreePredecessor</a>
 

 

