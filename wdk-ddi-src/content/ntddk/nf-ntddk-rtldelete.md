---
UID: NF:ntddk.RtlDelete
title: RtlDelete function (ntddk.h)
description: The RtlDelete routine deletes the specified node from the splay link tree.
old-location: ifsk\rtldelete.htm
tech.root: ifsk
ms.assetid: ca73b7cf-56c0-4e83-8804-59f73fbd4714
ms.date: 04/16/2018
keywords: ["RtlDelete function"]
ms.keywords: RtlDelete, RtlDelete routine [Installable File System Drivers], ifsk.rtldelete, ntddk/RtlDelete, rtlref_637fb420-7027-4426-a4a0-7ae887ad1950.xml
f1_keywords:
 - "ntddk/RtlDelete"
 - "RtlDelete"
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlDelete
targetos: Windows
req.typenames: 
---

# RtlDelete function


## -description


The <b>RtlDelete</b> routine deletes the specified node from the splay link tree. 


## -parameters




### -param Links [in]

Pointer to the node to be deleted. The node must have been initialized by calling <b>RtlInitializeSplayLinks</b>.


## -returns



<b>RtlDelete</b> returns a pointer to the root of the splay link tree from which the given node was deleted, or it returns <b>NULL</b> if the tree is empty. 




## -remarks



<b>RtlDelete</b> rebalances the splay link tree after the node is deleted. To delete a node without rebalancing the tree, use <b>RtlDeleteNoSplay</b> instead of <b>RtlDelete</b>.

Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlDelete</b> must be running at IRQL <= DISPATCH_LEVEL if the splay link tree is nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtldeletenosplay">RtlDeleteNoSplay</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializesplaylinks">RtlInitializeSplayLinks</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinsertasleftchild">RtlInsertAsLeftChild</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinsertasrightchild">RtlInsertAsRightChild</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlsplay">RtlSplay</a>
 

 

