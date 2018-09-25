---
UID: NF:ntifs.FsRtlInitExtraCreateParameterLookasideList
title: FsRtlInitExtraCreateParameterLookasideList function
author: windows-driver-content
description: The FsRtlInitExtraCreateParameterLookasideList routine initializes a paged or nonpaged pool lookaside list used for the allocation of one or more extra create parameter context structures (ECPs) of fixed size.
old-location: ifsk\fsrtlinitextracreateparameterlookasidelist.htm
tech.root: ifsk
ms.assetid: 30ad87de-a371-415b-b77f-513369fed098
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FsRtlInitExtraCreateParameterLookasideList, FsRtlInitExtraCreateParameterLookasideList routine [Installable File System Drivers], fsrtlref_4b4e21ec-cfcc-45b7-bcb9-74dbc7c486ac.xml, ifsk.fsrtlinitextracreateparameterlookasidelist, ntifs/FsRtlInitExtraCreateParameterLookasideList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlInitExtraCreateParameterLookasideList routine is available starting with Windows Vista.
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlInitExtraCreateParameterLookasideList
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlInitExtraCreateParameterLookasideList function


## -description


The <b>FsRtlInitExtraCreateParameterLookasideList</b> routine initializes a paged or nonpaged pool lookaside list used for the allocation of one or more extra create parameter context structures (ECPs) of fixed size.


## -parameters




### -param Lookaside [in, out]

Pointer to an opaque <a href="https://msdn.microsoft.com/library/windows/hardware/ff558775">PAGED_LOOKASIDE_LIST</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff556431">NPAGED_LOOKASIDE_LIST</a> lookaside list-head structure. For a paged or nonpaged lookaside list, the list-head structure must be allocated from nonpaged pool. 


### -param Flags [in]

Defines pool allocation options. If the <i>Flags</i> parameter contains the FSRTL_ECP_LOOKASIDE_FLAG_NONPAGED_POOL bit flag value, <b>FsRtlInitExtraCreateParameterLookasideList</b> initializes a lookaside list for nonpaged ECP entries of the specified size. Otherwise, <b>FsRtlInitExtraCreateParameterLookasideList</b> initializes a lookaside list for paged ECP entries of the specified size. 


### -param Size [in]

Specifies the size, in bytes, for all ECP entries in the lookaside list. 


### -param Tag [in]

Specifies the pool tag to use when allocating lookaside list ECP entries. For more information about pool tags, see the <i>Tag</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a>. 


## -returns



None




## -remarks



Use this routine to initialize a paged or nonpaged pool lookaside list. Use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545616">FsRtlAllocateExtraCreateParameterFromLookasideList</a> routine to allocate an ECP from the lookaside list, and the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545989">FsRtlFreeExtraCreateParameter</a> routine to return an ECP buffer to the lookaside list for recycling.

Use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545849">FsRtlDeleteExtraCreateParameterLookasideList</a> routine to free the lookaside list itself.

Drivers must free all ECPs and lookaside lists that they create before they unload.

For more information on using lookaside lists with drivers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565416">Using Lookaside Lists</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545616">FsRtlAllocateExtraCreateParameterFromLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545849">FsRtlDeleteExtraCreateParameterLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545989">FsRtlFreeExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556431">NPAGED_LOOKASIDE_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558775">PAGED_LOOKASIDE_LIST</a>
 

 

