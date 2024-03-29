---
UID: NF:ntddk.RtlDeleteNoSplay
title: RtlDeleteNoSplay function (ntddk.h)
description: The RtlDeleteNoSplay routine deletes the specified node from the splay link tree.
old-location: ifsk\rtldeletenosplay.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["RtlDeleteNoSplay function"]
ms.keywords: RtlDeleteNoSplay, RtlDeleteNoSplay routine [Installable File System Drivers], ifsk.rtldeletenosplay, ntddk/RtlDeleteNoSplay, rtlref_def5bfa8-367a-410e-8e3c-fdbf11cce05e.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlDeleteNoSplay
 - ntddk/RtlDeleteNoSplay
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlDeleteNoSplay
---

# RtlDeleteNoSplay function


## -description

The <b>RtlDeleteNoSplay</b> routine deletes the specified node from the splay link tree.

## -parameters

### -param Links [in]


A pointer to the node to be deleted. The node must have been initialized by calling <b>RtlInitializeSplayLinks</b>.

### -param Root [in, out]


A pointer to the caller's pointer to the root node of the splay link tree. The caller's pointer is updated after the node is deleted.

## -returns

None

## -remarks

Unlike <b>RtlDelete</b>, <b>RtlDeleteNoSplay</b> does not rebalance the splay link tree after the node is deleted. 

Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlDeleteNoSplay</b> must be running at IRQL <= DISPATCH_LEVEL if the splay link tree is nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtldelete">RtlDelete</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializesplaylinks">RtlInitializeSplayLinks</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinsertasleftchild">RtlInsertAsLeftChild</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinsertasrightchild">RtlInsertAsRightChild</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlsplay">RtlSplay</a>
