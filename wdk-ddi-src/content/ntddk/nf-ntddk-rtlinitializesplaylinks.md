---
UID: NF:ntddk.RtlInitializeSplayLinks
title: RtlInitializeSplayLinks function
description: The RtlInitializeSplayLinks routine initializes a splay link node.
old-location: ifsk\rtlinitializesplaylinks.htm
tech.root: ifsk
ms.assetid: 34818dc0-d241-4f5f-a202-08200fbc23a3
ms.date: 04/16/2018
ms.keywords: RtlInitializeSplayLinks, RtlInitializeSplayLinks routine [Installable File System Drivers], ifsk.rtlinitializesplaylinks, ntddk/RtlInitializeSplayLinks, rtlref_20e818cf-6afb-4699-b760-bbd7964b576c.xml
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
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
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	RtlInitializeSplayLinks
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlInitializeSplayLinks function


## -description


The <b>RtlInitializeSplayLinks</b> routine initializes a splay link node. 


## -parameters




### -param Links [in]

Pointer to a caller-allocated buffer, which must be at least <b>sizeof(</b>RTL_SPLAY_LINK<b>)</b>, to contain the initialized splay link node. 


## -returns



None




## -remarks



Every splay link node, including the initial root node of the splay link tree, must be initialized by calling <b>RtlInitializeSplayLinks</b> before it is passed to any other <b>Rtl</b> splay link routine. The initialized splay link node structure should be considered opaque.

Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlInitializeSplayLinks</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the memory at <i>Links</i> is nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545293">ExInitializeFastMutex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552214">RtlDeleteNoSplay</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553017">RtlInsertAsLeftChild</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553022">RtlInsertAsRightChild</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553054">RtlIsLeftChild</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553066">RtlIsRightChild</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553072">RtlIsRoot</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553080">RtlLeftChild</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553165">RtlParent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553186">RtlRealPredecessor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553188">RtlRealSuccessor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553200">RtlRightChild</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553226">RtlSplay</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553237">RtlSubtreePredecessor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553239">RtlSubtreeSuccessor</a>
 

 

