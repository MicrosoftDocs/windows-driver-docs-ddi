---
UID: NF:ntddk.RtlInsertAsRightChild
title: RtlInsertAsRightChild function (ntddk.h)
description: The RtlInsertAsRightChild routine inserts a given splay link into the tree as the right child of a given node in that tree.
old-location: ifsk\rtlinsertasrightchild.htm
tech.root: ifsk
ms.assetid: eaeff5fe-a678-44e5-a78d-ef4816708878
ms.date: 04/16/2018
keywords: ["RtlInsertAsRightChild function"]
ms.keywords: RtlInsertAsRightChild, RtlInsertAsRightChild routine [Installable File System Drivers], ifsk.rtlinsertasrightchild, ntddk/RtlInsertAsRightChild, rtlref_e16d0af2-9299-4fda-96ad-75a39f3e505f.xml
f1_keywords:
 - "ntddk/RtlInsertAsRightChild"
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
- RtlInsertAsRightChild
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlInsertAsRightChild function


## -description


The <b>RtlInsertAsRightChild</b> routine inserts a given splay link into the tree as the right child of a given node in that tree. 


## -parameters




### -param ParentLinks [in]

Pointer to the node in the tree at which <i>ChildLinks</i> should be inserted as the right child. 


### -param ChildLinks [in]

Pointer to the splay link node to be inserted into the tree. The node must have been initialized by calling <b>RtlInitializeSplayLinks</b>. 


## -remarks



Callers of <b>RtlInsertAsRightChild</b> are responsible for meeting the following criteria:

<ul>
<li>
The node at <i>ParentLinks</i> must have no right child. 

A caller can determine whether the node already has a right child by calling <b>RtlRightChild</b>. If <b>RtlRightChild</b> returns <b>NULL</b>, <i>ParentLinks</i> is a valid parameter to <b>RtlInsertAsRightChild</b>.

</li>
<li>
The node at <i>ChildLinks</i> must have no parent.

A caller can determine whether this node already has a parent by calling <b>RtlIsRoot</b> or <b>RtlParent</b>. If <b>RtlIsRoot</b> returns <b>TRUE</b> when called with <i>ChildLinks</i>, <i>ChildLinks</i> is a valid parameter to <b>RtlInsertAsRightChild</b>. If <b>RtlParent</b> returns an equivalent pointer to <i>ChildLinks</i>, <i>ChildLinks</i> is also a valid parameter to <b>RtlInsertAsRightChild</b>. 

</li>
</ul>
Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlInsertAsRightChild</b> must be running at IRQL <= DISPATCH_LEVEL if the splay link tree and <i>ChildLinks</i> node are nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializesplaylinks">RtlInitializeSplayLinks</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinsertasleftchild">RtlInsertAsLeftChild</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlisroot">RtlIsRoot</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlparent">RtlParent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlrightchild">RtlRightChild</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlsplay">RtlSplay</a>
 

 

