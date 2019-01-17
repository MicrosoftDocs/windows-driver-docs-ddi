---
UID: NF:ntifs.FsRtlDeleteExtraCreateParameterLookasideList
title: FsRtlDeleteExtraCreateParameterLookasideList function
description: The FsRtlDeleteExtraCreateParameterLookasideList routine frees an extra create parameter (ECP) lookaside list.
old-location: ifsk\fsrtldeleteextracreateparameterlookasidelist.htm
tech.root: ifsk
ms.assetid: 786635b4-db99-4b35-9fb5-23233997d091
ms.date: 04/16/2018
ms.keywords: FsRtlDeleteExtraCreateParameterLookasideList, FsRtlDeleteExtraCreateParameterLookasideList routine [Installable File System Drivers], fsrtlref_43144ea3-5cbc-43ce-b3f8-4101b1e3aeaa.xml, ifsk.fsrtldeleteextracreateparameterlookasidelist, ntifs/FsRtlDeleteExtraCreateParameterLookasideList
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: FsRtlDeleteExtraCreateParameterLookasideList is available starting with Windows Vista.
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
-	FsRtlDeleteExtraCreateParameterLookasideList
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlDeleteExtraCreateParameterLookasideList function


## -description


The <b>FsRtlDeleteExtraCreateParameterLookasideList </b>routine frees an extra create parameter (ECP) lookaside list.


## -parameters




### -param Lookaside [in, out]

Pointer to an opaque <a href="https://msdn.microsoft.com/library/windows/hardware/ff558775">PAGED_LOOKASIDE_LIST</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff556431">NPAGED_LOOKASIDE_LIST</a> lookaside list-head structure that represents the lookaside list to be freed.


### -param Flags [in]

Communicates ECP lookaside list allocation options with which the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546102">FsRtlInitExtraCreateParameterLookasideList</a> routine initialized the lookaside list.

This <i>Flags</i> parameter should be the same as the <i>Flags</i> parameter used in the call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546102">FsRtlInitExtraCreateParameterLookasideList</a> routine.


## -returns



None




## -remarks



The <b>FsRtlDeleteExtraCreateParameterLookasideList</b> routine frees the ECP lookaside list to which the <i>Lookaside</i> parameter points. However, freeing the lookaside list does not automatically free any ECP context structures allocated from the lookaside list. To free an ECP context structure allocated from a lookaside list, call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545989">FsRtlFreeExtraCreateParameter</a> routine.

Drivers must explicitly free all ECP context structures and ECP lookaside lists that they created before unloading. For more information about using lookaside lists, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565416">Using Lookaside Lists</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545989">FsRtlFreeExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546102">FsRtlInitExtraCreateParameterLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556431">NPAGED_LOOKASIDE_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558775">PAGED_LOOKASIDE_LIST</a>
 

 

