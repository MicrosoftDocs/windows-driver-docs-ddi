---
UID: NF:ntddk.RtlIsLeftChild
title: RtlIsLeftChild macro
author: windows-driver-content
description: The RtlIsLeftChild routine determines whether a given splay link is the left child of a node in a splay link tree.
old-location: ifsk\rtlisleftchild.htm
old-project: ifsk
ms.assetid: 6ccdcc68-f03f-4972-91de-c8ab7f4389fb
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RtlIsLeftChild
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
req.alt-api: RtlIsLeftChild
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
req.irql: See Remarks section.
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# RtlIsLeftChild macro



## -description
The <b>RtlIsLeftChild</b> routine determines whether a given splay link is the left child of a node in a splay link tree. 



## -syntax

````
BOOLEAN RtlIsLeftChild(
  _In_ PRTL_SPLAY_LINKS Links
);
````


## -parameters

### -param Links [in]

Pointer to the node. The node must have been initialized by calling <b>RtlInitializeSplayLinks</b>.


## -remarks
The given node at <i>Links</i> must have a parent node in the tree. A caller can determine whether this node has a parent with <b>RtlIsRoot</b>. If <b>RtlIsRoot</b> returns <b>FALSE</b>, <i>Links</i> is a valid parameter to <b>RtlIsLeftChild</b>. 

Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlIsLeftChild</b> can be running at IRQL &lt;= DISPATCH_LEVEL if the splay link tree is nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL. 


## -see-also
<dl>
<dt>
<a href="..\ntddk\nf-ntddk-rtlinitializesplaylinks.md">RtlInitializeSplayLinks</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlisrightchild.md">RtlIsRightChild</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlisroot.md">RtlIsRoot</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlleftchild.md">RtlLeftChild</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlsplay.md">RtlSplay</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlIsLeftChild routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

