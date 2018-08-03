---
UID: NF:ntddk.RtlIsLeftChild
title: RtlIsLeftChild macro
author: windows-driver-content
description: The RtlIsLeftChild routine determines whether a given splay link is the left child of a node in a splay link tree.
old-location: ifsk\rtlisleftchild.htm
tech.root: ifsk
ms.assetid: 6ccdcc68-f03f-4972-91de-c8ab7f4389fb
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: RtlIsLeftChild, RtlIsLeftChild routine [Installable File System Drivers], ifsk.rtlisleftchild, ntddk/RtlIsLeftChild, rtlref_2692597e-5133-48f2-b978-c8ac5f2280fe.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
-	RtlIsLeftChild
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlIsLeftChild macro


## -description


The <b>RtlIsLeftChild</b> routine determines whether a given splay link is the left child of a node in a splay link tree. 


## -parameters




### -param Links [in]

Pointer to the node. The node must have been initialized by calling <b>RtlInitializeSplayLinks</b>.


## -remarks



The given node at <i>Links</i> must have a parent node in the tree. A caller can determine whether this node has a parent with <b>RtlIsRoot</b>. If <b>RtlIsRoot</b> returns <b>FALSE</b>, <i>Links</i> is a valid parameter to <b>RtlIsLeftChild</b>. 

Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlIsLeftChild</b> can be running at IRQL &lt;= DISPATCH_LEVEL if the splay link tree is nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553010">RtlInitializeSplayLinks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553066">RtlIsRightChild</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553072">RtlIsRoot</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553080">RtlLeftChild</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553226">RtlSplay</a>
 

 

