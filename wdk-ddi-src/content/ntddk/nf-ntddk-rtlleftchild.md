---
UID: NF:ntddk.RtlLeftChild
title: RtlLeftChild macro (ntddk.h)
description: The RtlLeftChild routine returns a pointer to the left child of the specified splay link node.
old-location: ifsk\rtlleftchild.htm
tech.root: ifsk
ms.assetid: 26e6b0c6-7de0-43c9-a117-5c0bf0e986a2
ms.date: 04/16/2018
keywords: ["RtlLeftChild macro"]
ms.keywords: RtlLeftChild, RtlLeftChild routine [Installable File System Drivers], ifsk.rtlleftchild, ntddk/RtlLeftChild, rtlref_f2bfae7c-de1d-4d7c-84b5-947a0cfdb16f.xml
f1_keywords:
 - "ntddk/RtlLeftChild"
 - "RtlLeftChild"
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
- RtlLeftChild
targetos: Windows
req.typenames: 
---

# RtlLeftChild macro


## -description


The <b>RtlLeftChild</b> routine returns a pointer to the left child of the specified splay link node. 


## -parameters




### -param Links 
[in]
Pointer to the node whose left child is to be returned. The node must have been initialized by calling <b>RtlInitializeSplayLinks</b>. 


## -remarks

**RtlLeftChild** returns a pointer to the left child of the node at Links, or it returns NULL if the specified node has no left child. 


<b>RtlLeftChild</b> can be called repeatedly in conjunction with <b>RtlParent</b> and <b>RtlRightChild</b> to walk a splay link tree. 

Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlLeftChild</b> must be running at IRQL <= DISPATCH_LEVEL if the tree is nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializesplaylinks">RtlInitializeSplayLinks</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinsertasleftchild">RtlInsertAsLeftChild</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlparent">RtlParent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlrightchild">RtlRightChild</a>
 

 

