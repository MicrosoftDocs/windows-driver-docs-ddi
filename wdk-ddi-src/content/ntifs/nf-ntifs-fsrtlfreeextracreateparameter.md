---
UID: NF:ntifs.FsRtlFreeExtraCreateParameter
title: FsRtlFreeExtraCreateParameter function (ntifs.h)
description: The FsRtlFreeExtraCreateParameter routine frees the memory for an ECP context structure.
old-location: ifsk\fsrtlfreeextracreateparameter.htm
tech.root: ifsk
ms.assetid: c46cdfd3-36c4-420d-9dbf-d6f0bede460e
ms.date: 04/16/2018
ms.keywords: FsRtlFreeExtraCreateParameter, FsRtlFreeExtraCreateParameter routine [Installable File System Drivers], fsrtlref_bbee8298-87e1-4487-bf56-b2dd76913d47.xml, ifsk.fsrtlfreeextracreateparameter, ntifs/FsRtlFreeExtraCreateParameter
ms.topic: function
f1_keywords:
 - "ntifs/FsRtlFreeExtraCreateParameter"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlFreeExtraCreateParameter routine is available starting with Windows Vista.
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlFreeExtraCreateParameter
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlFreeExtraCreateParameter function


## -description


The <b>FsRtlFreeExtraCreateParameter</b> routine frees the memory for an ECP context structure.


## -parameters




### -param EcpContext [in]

Pointer to the extra create parameter (ECP) context structure to be freed.


## -returns



None




## -remarks



If the ECP context structure to be freed is still attached to an ECP list, it must first be detached from the list by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltremoveextracreateparameter">FltRemoveExtraCreateParameter</a> routine before the <b>FsRtlFreeExtraCreateParameter</b> routine can free it.

If a cleanup callback routine of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff551124">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a> was defined for the given ECP context structure, this callback routine is invoked upon deletion of the ECP context structure.  




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff540148(v=vs.85)">ECP_LIST</a>



<b>FltAllocateExtraCreateParameterFromLookasideList</b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcreatefileex2">FltCreateFileEx2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltfreeextracreateparameter">FltFreeExtraCreateParameter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltgetecplistfromcallbackdata">FltGetEcpListFromCallbackData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltinsertextracreateparameter">FltInsertExtraCreateParameter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltremoveextracreateparameter">FltRemoveExtraCreateParameter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltsetecplistintocallbackdata">FltSetEcpListIntoCallbackData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-iocreatefileex">IoCreateFileEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551124">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a>
 

 

