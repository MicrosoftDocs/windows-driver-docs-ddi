---
UID: NF:ntddk.RtlInitializeSplayLinks
title: RtlInitializeSplayLinks function (ntddk.h)
description: The RtlInitializeSplayLinks routine initializes a splay link node.
old-location: ifsk\rtlinitializesplaylinks.htm
tech.root: ifsk
ms.assetid: 34818dc0-d241-4f5f-a202-08200fbc23a3
ms.date: 04/16/2018
keywords: ["RtlInitializeSplayLinks function"]
ms.keywords: RtlInitializeSplayLinks, RtlInitializeSplayLinks routine [Installable File System Drivers], ifsk.rtlinitializesplaylinks, ntddk/RtlInitializeSplayLinks, rtlref_20e818cf-6afb-4699-b760-bbd7964b576c.xml
f1_keywords:
 - "ntddk/RtlInitializeSplayLinks"
 - "RtlInitializeSplayLinks"
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
- RtlInitializeSplayLinks
targetos: Windows
req.typenames: 
---

# RtlInitializeSplayLinks function


## -description


The <b>RtlInitializeSplayLinks</b> routine initializes a splay link node. 


## -parameters




### -param Links 
[in]
Pointer to a caller-allocated buffer, which must be at least <b>sizeof(</b>RTL_SPLAY_LINK<b>)</b>, to contain the initialized splay link node. 


## -remarks



Every splay link node, including the initial root node of the splay link tree, must be initialized by calling <b>RtlInitializeSplayLinks</b> before it is passed to any other <b>Rtl</b> splay link routine. The initialized splay link node structure should be considered opaque.

Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlInitializeSplayLinks</b> must be running at IRQL <= DISPATCH_LEVEL if the memory at <i>Links</i> is nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializefastmutex">ExInitializeFastMutex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtldeletenosplay">RtlDeleteNoSplay</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinsertasleftchild">RtlInsertAsLeftChild</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinsertasrightchild">RtlInsertAsRightChild</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlisleftchild">RtlIsLeftChild</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlisrightchild">RtlIsRightChild</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlisroot">RtlIsRoot</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlleftchild">RtlLeftChild</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlparent">RtlParent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlrealpredecessor">RtlRealPredecessor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlrealsuccessor">RtlRealSuccessor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlrightchild">RtlRightChild</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlsplay">RtlSplay</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlsubtreepredecessor">RtlSubtreePredecessor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlsubtreesuccessor">RtlSubtreeSuccessor</a>
 

 

