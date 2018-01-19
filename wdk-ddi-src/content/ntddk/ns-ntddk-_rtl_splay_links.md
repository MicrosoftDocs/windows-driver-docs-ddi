---
UID: NS:ntddk._RTL_SPLAY_LINKS
title: _RTL_SPLAY_LINKS
author: windows-driver-content
description: The RTL_SPLAY_LINKS structure is an opaque structure and is used by the system to represent a splay link tree node.
old-location: ifsk\rtl_splay_links.htm
old-project: ifsk
ms.assetid: b035b101-2667-4962-ae49-781ddd30e0be
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _RTL_SPLAY_LINKS, RTL_SPLAY_LINKS, *PRTL_SPLAY_LINKS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Fltkernel.h, Ntifs.h, Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Available in all supported versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RTL_SPLAY_LINKS
req.alt-loc: ntddk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: RTL_SPLAY_LINKS
---

# _RTL_SPLAY_LINKS structure



## -description
The RTL_SPLAY_LINKS structure is an opaque structure and is used by the system to represent a splay link tree node.



## -syntax

````
typedef struct _RTL_SPLAY_LINKS {
  struct _RTL_SPLAY_LINKS  *Parent;
  struct _RTL_SPLAY_LINKS  *LeftChild;
  struct _RTL_SPLAY_LINKS  *RightChild;
} RTL_SPLAY_LINKS, *PRTL_SPLAY_LINKS;
````


## -struct-fields

### -field Parent

An opaque pointer to the parent node for this node.  If only one node in the splay link tree exists, the value of this member is <b>NULL</b>.


### -field LeftChild

An opaque pointer to the left child node for this node.  If no left-child node exists, the value of this member is <b>NULL</b>.


### -field RightChild

An opaque pointer to the right child node for this node.  If no right-child node exists, the value of this member is <b>NULL</b>.


## -remarks
Typically, each node of a splay link tree consists of a user-defined structure.  Each such user-defined node must contain an initialized RTL_SPLAY_LINKS structure. To initialize a RTL_SPLAY_LINKS structure, call the <a href="..\ntddk\nf-ntddk-rtlinitializesplaylinks.md">RtlInitializeSplayLinks</a> macro.  (Pass the address of the RTL_SPLAY_LINKS member that is contained within the user-defined structure.)

For a splay link tree with one or more nodes, a new node is generally initialized as follows:

Use <a href="..\ntddk\nf-ntddk-rtlleftchild.md">RtlLeftChild</a> and/or <a href="..\ntddk\nf-ntddk-rtlrightchild.md">RtlRightChild</a> to find the insertion point for the new node.  That is, obtain the correct address of the parent node for the new node.  (The new node will be attached either to the left of the parent node or to the right.)

Use <a href="..\ntddk\nf-ntddk-rtlinitializesplaylinks.md">RtlInitializeSplayLinks</a> to initialize the new node with the address of the parent node that is found in the previous step.

Insert the new node into the splay tree by using either <a href="..\ntddk\nf-ntddk-rtlinsertasleftchild.md">RtlInsertAsLeftChild</a> or <a href="..\ntddk\nf-ntddk-rtlinsertasrightchild.md">RtlInsertAsRightChild</a>, as appropriate.

Call <a href="..\ntddk\nf-ntddk-rtlsplay.md">RtlSplay</a> with the address of the new node. (The new node becomes the root of the splay tree.)

Callers of the <b>Rtl</b><b><i>Xxx</i></b> splay tree routines are responsible for synchronizing access to the splay tree. For more information about how to synchronize access to the splay tree, see <a href="http://go.microsoft.com/fwlink/p/?linkid=120487">Locks, Deadlocks, and Synchronization</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff554368">Managing Hardware Priorities</a>.


## -see-also
<dl>
<dt>
<a href="..\ntddk\nf-ntddk-rtlinitializesplaylinks.md">RtlInitializeSplayLinks</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlinsertasleftchild.md">RtlInsertAsLeftChild</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlinsertasrightchild.md">RtlInsertAsRightChild</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlleftchild.md">RtlLeftChild</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlrightchild.md">RtlRightChild</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlsplay.md">RtlSplay</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RTL_SPLAY_LINKS structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

