---
UID: NS:ntddk._RTL_SPLAY_LINKS
title: _RTL_SPLAY_LINKS (ntddk.h)
description: The RTL_SPLAY_LINKS structure is an opaque structure and is used by the system to represent a splay link tree node.
old-location: ifsk\rtl_splay_links.htm
tech.root: ifsk
ms.assetid: b035b101-2667-4962-ae49-781ddd30e0be
ms.date: 04/16/2018
keywords: ["RTL_SPLAY_LINKS structure"]
ms.keywords: "*PRTL_SPLAY_LINKS, PRTL_SPLAY_LINKS, PRTL_SPLAY_LINKS structure pointer [Installable File System Drivers], RTL_SPLAY_LINKS, RTL_SPLAY_LINKS structure [Installable File System Drivers], _RTL_SPLAY_LINKS, ifsk.rtl_splay_links, ntddk/PRTL_SPLAY_LINKS, ntddk/RTL_SPLAY_LINKS, othersystemstructures_3a91f0e3-8f7c-4f45-8707-2392d2637cf4.xml"
req.header: ntddk.h
req.include-header: Fltkernel.h, Ntifs.h, Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Available in all supported versions of Windows.
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
req.irql: 
targetos: Windows
req.typenames: RTL_SPLAY_LINKS
f1_keywords:
 - _RTL_SPLAY_LINKS
 - ntddk/_RTL_SPLAY_LINKS
 - RTL_SPLAY_LINKS
 - ntddk/RTL_SPLAY_LINKS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - RTL_SPLAY_LINKS
---

# _RTL_SPLAY_LINKS structure


## -description

The RTL_SPLAY_LINKS structure is an opaque structure and is used by the system to represent a splay link tree node.

## -struct-fields

### -field Parent

An opaque pointer to the parent node for this node.  If only one node in the splay link tree exists, the value of this member is <b>NULL</b>.

### -field LeftChild

An opaque pointer to the left child node for this node.  If no left-child node exists, the value of this member is <b>NULL</b>.

### -field RightChild

An opaque pointer to the right child node for this node.  If no right-child node exists, the value of this member is <b>NULL</b>.

## -remarks

Typically, each node of a splay link tree consists of a user-defined structure.  Each such user-defined node must contain an initialized RTL_SPLAY_LINKS structure. To initialize a RTL_SPLAY_LINKS structure, call the <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializesplaylinks">RtlInitializeSplayLinks</a> macro.  (Pass the address of the RTL_SPLAY_LINKS member that is contained within the user-defined structure.)

For a splay link tree with one or more nodes, a new node is generally initialized as follows:

<ol>
<li>
Use <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlleftchild">RtlLeftChild</a> and/or <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlrightchild">RtlRightChild</a> to find the insertion point for the new node.  That is, obtain the correct address of the parent node for the new node.  (The new node will be attached either to the left of the parent node or to the right.)

</li>
<li>
Use <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializesplaylinks">RtlInitializeSplayLinks</a> to initialize the new node with the address of the parent node that is found in the previous step.

</li>
<li>
Insert the new node into the splay tree by using either <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinsertasleftchild">RtlInsertAsLeftChild</a> or <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinsertasrightchild">RtlInsertAsRightChild</a>, as appropriate.

</li>
<li>
Call <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlsplay">RtlSplay</a> with the address of the new node. (The new node becomes the root of the splay tree.)

</li>
</ol>
Callers of the <b>Rtl</b><b><i>Xxx</i></b> splay tree routines are responsible for synchronizing access to the splay tree. For more information about how to synchronize access to the splay tree, see <a href="/previous-versions/ms810047(v=msdn.10)">Locks, Deadlocks, and Synchronization</a> and <a href="/windows-hardware/drivers/kernel/managing-hardware-priorities">Managing Hardware Priorities</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializesplaylinks">RtlInitializeSplayLinks</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinsertasleftchild">RtlInsertAsLeftChild</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinsertasrightchild">RtlInsertAsRightChild</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlleftchild">RtlLeftChild</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlrightchild">RtlRightChild</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlsplay">RtlSplay</a>