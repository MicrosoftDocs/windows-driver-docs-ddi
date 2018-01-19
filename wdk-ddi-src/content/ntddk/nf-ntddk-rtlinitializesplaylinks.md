---
UID: NF:ntddk.RtlInitializeSplayLinks
title: RtlInitializeSplayLinks function
author: windows-driver-content
description: The RtlInitializeSplayLinks routine initializes a splay link node.
old-location: ifsk\rtlinitializesplaylinks.htm
old-project: ifsk
ms.assetid: 34818dc0-d241-4f5f-a202-08200fbc23a3
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RtlInitializeSplayLinks
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
req.alt-api: RtlInitializeSplayLinks
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

# RtlInitializeSplayLinks function



## -description
The <b>RtlInitializeSplayLinks</b> routine initializes a splay link node. 



## -syntax

````
VOID RtlInitializeSplayLinks(
  _In_ PRTL_SPLAY_LINKS Links
);
````


## -parameters

### -param Links [in]

Pointer to a caller-allocated buffer, which must be at least <b>sizeof(</b>RTL_SPLAY_LINK<b>)</b>, to contain the initialized splay link node. 


## -returns
None


## -remarks
Every splay link node, including the initial root node of the splay link tree, must be initialized by calling <b>RtlInitializeSplayLinks</b> before it is passed to any other <b>Rtl</b> splay link routine. The initialized splay link node structure should be considered opaque.

Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlInitializeSplayLinks</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the memory at <i>Links</i> is nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL. 


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-exinitializefastmutex.md">ExInitializeFastMutex</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtldeletenosplay.md">RtlDeleteNoSplay</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlinsertasleftchild.md">RtlInsertAsLeftChild</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlinsertasrightchild.md">RtlInsertAsRightChild</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlisleftchild.md">RtlIsLeftChild</a>
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
<a href="..\ntddk\nf-ntddk-rtlparent.md">RtlParent</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlrealpredecessor.md">RtlRealPredecessor</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlrealsuccessor.md">RtlRealSuccessor</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlrightchild.md">RtlRightChild</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlsplay.md">RtlSplay</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlsubtreepredecessor.md">RtlSubtreePredecessor</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlsubtreesuccessor.md">RtlSubtreeSuccessor</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlInitializeSplayLinks routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

