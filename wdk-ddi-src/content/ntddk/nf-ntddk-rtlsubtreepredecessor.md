---
UID: NF:ntddk.RtlSubtreePredecessor
title: RtlSubtreePredecessor function
author: windows-driver-content
description: The RtlSubtreePredecessor routine returns a pointer to the predecessor of the specified node within the subtree that is rooted at that node.
old-location: ifsk\rtlsubtreepredecessor.htm
old-project: ifsk
ms.assetid: 19c1bea8-dba7-45a5-9620-0d6a928019ce
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: RtlSubtreePredecessor, RtlSubtreePredecessor routine [Installable File System Drivers], ifsk.rtlsubtreepredecessor, ntddk/RtlSubtreePredecessor, rtlref_0d0ea0f4-2b16-4d9c-8747-78d6ddcc90d6.xml
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
-	RtlSubtreePredecessor
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlSubtreePredecessor function


## -description


The <b>RtlSubtreePredecessor</b> routine returns a pointer to the predecessor of the specified node within the subtree that is rooted at that node. 


## -parameters




### -param Links [in]

A pointer to the node. The node must have been initialized by calling <b>RtlInitializeSplayLinks</b>. 


## -returns



<b>RtlSubtreePredecessor</b> returns a pointer to the subtree predecessor of the node at <i>Links</i>, or <b>NULL</b> if the node has no subtree predecessor. 




## -remarks



If the node at <i>Links</i> has a left subtree, the rightmost node of that subtree is the subtree predecessor. 

Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlSubtreePredecessor</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the tree is nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553010">RtlInitializeSplayLinks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553186">RtlRealPredecessor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553226">RtlSplay</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553239">RtlSubtreeSuccessor</a>
 

 

