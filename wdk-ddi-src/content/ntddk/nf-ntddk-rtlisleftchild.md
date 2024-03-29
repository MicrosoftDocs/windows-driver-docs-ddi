---
UID: NF:ntddk.RtlIsLeftChild
title: RtlIsLeftChild macro (ntddk.h)
description: The RtlIsLeftChild routine determines whether a given splay link is the left child of a node in a splay link tree.
old-location: ifsk\rtlisleftchild.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["RtlIsLeftChild macro"]
ms.keywords: RtlIsLeftChild, RtlIsLeftChild routine [Installable File System Drivers], ifsk.rtlisleftchild, ntddk/RtlIsLeftChild, rtlref_2692597e-5133-48f2-b978-c8ac5f2280fe.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlIsLeftChild
 - ntddk/RtlIsLeftChild
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - RtlIsLeftChild
---

# RtlIsLeftChild macro


## -description

The <b>RtlIsLeftChild</b> routine determines whether a given splay link is the left child of a node in a splay link tree.

## -parameters

### -param Links [in]


Pointer to the node. The node must have been initialized by calling <b>RtlInitializeSplayLinks</b>.

## -remarks

**RtlIsLeftChild** returns TRUE if the given node at Links is the left child of its parent node, FALSE otherwise. 


The given node at <i>Links</i> must have a parent node in the tree. A caller can determine whether this node has a parent with <b>RtlIsRoot</b>. If <b>RtlIsRoot</b> returns <b>FALSE</b>, <i>Links</i> is a valid parameter to <b>RtlIsLeftChild</b>. 

Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlIsLeftChild</b> can be running at IRQL <= DISPATCH_LEVEL if the splay link tree is nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializesplaylinks">RtlInitializeSplayLinks</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlisrightchild">RtlIsRightChild</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlisroot">RtlIsRoot</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlleftchild">RtlLeftChild</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlsplay">RtlSplay</a>
