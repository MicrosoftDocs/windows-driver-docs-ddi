---
UID: NF:ntddk.RtlInsertAsLeftChild
title: RtlInsertAsLeftChild function
author: windows-driver-content
description: The RtlInsertAsLeftChild routine inserts a splay link node into the tree as the left child of the specified node.
old-location: ifsk\rtlinsertasleftchild.htm
old-project: ifsk
ms.assetid: cbb027f2-be7d-4de4-abbe-a37b7430153f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlInsertAsLeftChild, RtlInsertAsLeftChild routine [Installable File System Drivers], ifsk.rtlinsertasleftchild, ntddk/RtlInsertAsLeftChild, rtlref_228b3b79-ee0c-4361-ac36-223991ed3615.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	RtlInsertAsLeftChild
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# RtlInsertAsLeftChild function


## -description


The <b>RtlInsertAsLeftChild</b> routine inserts a splay link node into the tree as the left child of the specified node. 


## -syntax


````
VOID RtlInsertAsLeftChild(
  _In_ PRTL_SPLAY_LINKS ParentLinks,
  _In_ PRTL_SPLAY_LINKS ChildLinks
);
````


## -parameters




### -param ParentLinks [in]

Pointer to the node in the tree at which <i>ChildLinks</i> should be inserted as the left child. 


### -param ChildLinks [in]

Pointer to the splay link node to be inserted into the tree. The node must have been initialized by calling <b>RtlInitializeSplayLinks</b>.


## -returns



None




## -remarks



Callers of <b>RtlInsertAsLeftChild</b> are must meet the following criteria:

<ul>
<li>
The node at <i>ParentLinks</i> must have no left child. 

A caller can determine whether the node already has a left child by calling <b>RtlLeftChild</b>. If <b>RtlLeftChild</b> returns <b>NULL</b>, <i>ParentLinks</i> is a valid parameter to <b>RtlInsertAsLeftChild</b>.

</li>
<li>
The node at <i>ChildLinks</i> must have no parent.

A caller can determine whether this node already has a parent by calling <b>RtlIsRoot</b> or <b>RtlParent</b>. If <b>RtlIsRoot</b> returns <b>TRUE</b> when called with <i>ChildLinks</i>, <i>ChildLinks</i> is a valid parameter to <b>RtlInsertAsLeftChild</b>. If <b>RtlParent</b> returns an equivalent pointer to <i>ChildLinks</i>, <i>ChildLinks</i> is a valid parameter to <b>RtlInsertAsLeftChild</b>. 

</li>
</ul>
Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlInsertAsLeftChild</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the splay link tree and <i>ChildLinks</i> node are nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL. 




## -see-also

<<<<<<< HEAD
<a href="..\ntddk\nf-ntddk-rtlparent.md">RtlParent</a>



<a href="..\ntddk\nf-ntddk-rtlsplay.md">RtlSplay</a>
=======
<a href="..\ntddk\nf-ntddk-rtlleftchild.md">RtlLeftChild</a>
>>>>>>> 7b6bd3b88106eb7b25c8489b98269eb870735b73



<a href="..\ntddk\nf-ntddk-rtlinitializesplaylinks.md">RtlInitializeSplayLinks</a>



<a href="..\ntddk\nf-ntddk-rtlinsertasrightchild.md">RtlInsertAsRightChild</a>



<<<<<<< HEAD
<a href="..\ntddk\nf-ntddk-rtlisroot.md">RtlIsRoot</a>
=======
<a href="..\ntddk\nf-ntddk-rtlparent.md">RtlParent</a>
>>>>>>> 7b6bd3b88106eb7b25c8489b98269eb870735b73



<a href="..\ntddk\nf-ntddk-rtlleftchild.md">RtlLeftChild</a>



<a href="..\ntddk\nf-ntddk-rtlinsertasrightchild.md">RtlInsertAsRightChild</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlInsertAsLeftChild routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

