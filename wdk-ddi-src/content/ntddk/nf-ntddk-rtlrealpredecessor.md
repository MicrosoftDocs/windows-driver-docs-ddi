---
UID: NF:ntddk.RtlRealPredecessor
title: RtlRealPredecessor function
author: windows-driver-content
description: The RtlRealPredecessor routine returns a pointer to the predecessor of the specified node in the splay link tree.
old-location: ifsk\rtlrealpredecessor.htm
old-project: ifsk
ms.assetid: 8cb981a4-7dea-4d42-bbde-35cf5494494b
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RtlRealPredecessor, RtlRealPredecessor routine [Installable File System Drivers], ifsk.rtlrealpredecessor, ntddk/RtlRealPredecessor, rtlref_1c872dd0-50cb-48ff-a7e4-e3c88b3b087f.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlRealPredecessor
product:
- Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
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

Callers of <b>RtlRealPredecessor</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the tree is nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553188">RtlRealSuccessor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553226">RtlSplay</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553237">RtlSubtreePredecessor</a>
 

 

