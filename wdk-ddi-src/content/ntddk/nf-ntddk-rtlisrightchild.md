---
UID: NF:ntddk.RtlIsRightChild
title: RtlIsRightChild macro (ntddk.h)
description: The RtlIsRightChild routine determines whether a given splay link is the right child of a node in a splay link tree.
old-location: ifsk\rtlisrightchild.htm
tech.root: ifsk
ms.assetid: 23951fb8-35ab-4a05-b09b-d7f69057a5ad
ms.date: 04/16/2018
keywords: ["RtlIsRightChild macro"]
ms.keywords: RtlIsRightChild, RtlIsRightChild routine [Installable File System Drivers], ifsk.rtlisrightchild, ntddk/RtlIsRightChild, rtlref_741652e3-af4f-4e7b-978a-e6355db283a9.xml
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
 - RtlIsRightChild
 - ntddk/RtlIsRightChild
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - RtlIsRightChild
---

# RtlIsRightChild macro


## -description

The <b>RtlIsRightChild</b> routine determines whether a given splay link is the right child of a node in a splay link tree.

## -parameters

### -param Links 

[in]
Pointer to the node. The node must have been initialized by calling <b>RtlInitializeSplayLinks</b>.

## -remarks

**RtlIsRightChild** returns TRUE if the given node at Links is the right child of its parent node, FALSE otherwise. 


The given node at <i>Links</i> must have a parent node in the tree. A caller can determine whether this node has a parent with <b>RtlIsRoot</b>. If <b>RtlIsRoot</b> returns <b>FALSE</b>, <i>Links</i> is a valid parameter to <b>RtlIsRightChild</b>. 

Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlIsRightChild</b> can be running at IRQL <= DISPATCH_LEVEL if the splay link tree is nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializesplaylinks">RtlInitializeSplayLinks</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlisleftchild">RtlIsLeftChild</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlisroot">RtlIsRoot</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlrightchild">RtlRightChild</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlsplay">RtlSplay</a>