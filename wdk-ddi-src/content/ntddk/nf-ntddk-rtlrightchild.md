---
UID: NF:ntddk.RtlRightChild
title: RtlRightChild macro (ntddk.h)
description: The RtlRightChild routine returns a pointer to the right child of the specified splay link node.
old-location: ifsk\rtlrightchild.htm
tech.root: ifsk
ms.assetid: 1b906983-b000-449b-8e82-46ade5384168
ms.date: 04/16/2018
ms.keywords: RtlRightChild, RtlRightChild routine [Installable File System Drivers], ifsk.rtlrightchild, ntddk/RtlRightChild, rtlref_be516cb5-c4a7-4eb7-8faa-eac591b0902d.xml
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddk.h
api_name:
- RtlRightChild
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlRightChild macro


## -description


The <b>RtlRightChild</b> routine returns a pointer to the right child of the specified splay link node. 


## -parameters




### -param Links [in]

Pointer to the node whose right child is to be returned. The node must have been initialized by calling <b>RtlInitializeSplayLinks</b>. 

## -returns
**RtlRightChild** returns a pointer to the right child of the node at Links, or it returns NULL if the specified node has no right child. 


## -remarks



<b>RtlRightChild</b> can be called repeatedly in conjunction with <b>RtlParent</b> and <b>RtlLeftChild</b> to walk a splay link tree. 

Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlRightChild</b> must be running at IRQL <= DISPATCH_LEVEL if the tree is nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553010">RtlInitializeSplayLinks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553022">RtlInsertAsRightChild</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553080">RtlLeftChild</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553165">RtlParent</a>
 

 

