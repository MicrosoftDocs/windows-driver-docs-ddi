---
UID: NF:ntddk.RtlIsRightChild
title: RtlIsRightChild macro
author: windows-driver-content
description: The RtlIsRightChild routine determines whether a given splay link is the right child of a node in a splay link tree.
old-location: ifsk\rtlisrightchild.htm
old-project: ifsk
ms.assetid: 23951fb8-35ab-4a05-b09b-d7f69057a5ad
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: RtlIsRightChild, RtlIsRightChild routine [Installable File System Drivers], ifsk.rtlisrightchild, ntddk/RtlIsRightChild, rtlref_741652e3-af4f-4e7b-978a-e6355db283a9.xml
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
-	RtlIsRightChild
product: Windows
targetos: Windows
req.typenames: 
---

# RtlIsRightChild macro


## -description


The <b>RtlIsRightChild</b> routine determines whether a given splay link is the right child of a node in a splay link tree. 


## -parameters




### -param Links [in]

Pointer to the node. The node must have been initialized by calling <b>RtlInitializeSplayLinks</b>. 


## -remarks



The given node at <i>Links</i> must have a parent node in the tree. A caller can determine whether this node has a parent with <b>RtlIsRoot</b>. If <b>RtlIsRoot</b> returns <b>FALSE</b>, <i>Links</i> is a valid parameter to <b>RtlIsRightChild</b>. 

Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlIsRightChild</b> can be running at IRQL &lt;= DISPATCH_LEVEL if the splay link tree is nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553010">RtlInitializeSplayLinks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553054">RtlIsLeftChild</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553072">RtlIsRoot</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553200">RtlRightChild</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553226">RtlSplay</a>
 

 

