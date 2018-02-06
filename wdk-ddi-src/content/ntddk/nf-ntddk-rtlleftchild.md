---
UID: NF:ntddk.RtlLeftChild
title: RtlLeftChild macro
author: windows-driver-content
description: The RtlLeftChild routine returns a pointer to the left child of the specified splay link node.
old-location: ifsk\rtlleftchild.htm
old-project: ifsk
ms.assetid: 26e6b0c6-7de0-43c9-a117-5c0bf0e986a2
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RtlLeftChild, RtlLeftChild routine [Installable File System Drivers], ifsk.rtlleftchild, ntddk/RtlLeftChild, rtlref_f2bfae7c-de1d-4d7c-84b5-947a0cfdb16f.xml
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
req.lib: ntddk.h
req.dll: 
req.irql: See Remarks section.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	RtlLeftChild
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# RtlLeftChild macro


## -description


The <b>RtlLeftChild</b> routine returns a pointer to the left child of the specified splay link node. 


## -syntax


````
PRTL_SPLAY_LINKS RtlLeftChild(
  _In_ PRTL_SPLAY_LINKS Links
);
````


## -parameters




### -param Links [in]

Pointer to the node whose left child is to be returned. The node must have been initialized by calling <b>RtlInitializeSplayLinks</b>. 


## -remarks


<b>RtlLeftChild</b> can be called repeatedly in conjunction with <b>RtlParent</b> and <b>RtlRightChild</b> to walk a splay link tree. 

Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlLeftChild</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the tree is nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL. 



## -see-also

<a href="..\ntddk\nf-ntddk-rtlinitializesplaylinks.md">RtlInitializeSplayLinks</a>

<a href="..\ntddk\nf-ntddk-rtlinsertasleftchild.md">RtlInsertAsLeftChild</a>

<a href="..\ntddk\nf-ntddk-rtlparent.md">RtlParent</a>

<a href="..\ntddk\nf-ntddk-rtlrightchild.md">RtlRightChild</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlLeftChild routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

