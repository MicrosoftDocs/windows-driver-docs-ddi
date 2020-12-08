---
UID: NF:ntifs.FsRtlFreeExtraCreateParameterList
title: FsRtlFreeExtraCreateParameterList function (ntifs.h)
description: The FsRtlFreeExtraCreateParameterList routine frees an extra create parameter (ECP) list structure.
old-location: ifsk\fsrtlfreeextracreateparameterlist.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FsRtlFreeExtraCreateParameterList function"]
ms.keywords: FsRtlFreeExtraCreateParameterList, FsRtlFreeExtraCreateParameterList routine [Installable File System Drivers], fsrtlref_909d50be-4f8d-47dc-ad00-03d3f9eb4533.xml, ifsk.fsrtlfreeextracreateparameterlist, ntifs/FsRtlFreeExtraCreateParameterList
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlFreeExtraCreateParameterList routine is available starting with Windows Vista.
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlFreeExtraCreateParameterList
 - ntifs/FsRtlFreeExtraCreateParameterList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlFreeExtraCreateParameterList
---

# FsRtlFreeExtraCreateParameterList function


## -description

The <b>FsRtlFreeExtraCreateParameterList</b> routine frees an extra create parameter (ECP) list structure.

## -parameters

### -param EcpList 

[in]
Pointer to the ECP list structure to be freed.

## -remarks

<b>FsRtlFreeExtraCreateParameterList</b> frees an ECP list structure including any list elements, if they exist.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/ff540148(v=vs.85)">ECP_LIST</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocateextracreateparameterfromlookasidelist">FltAllocateExtraCreateParameterFromLookasideList</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocateextracreateparameterlist">FltAllocateExtraCreateParameterList</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefileex2">FltCreateFileEx2</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreeextracreateparameter">FltFreeExtraCreateParameter</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetecplistfromcallbackdata">FltGetEcpListFromCallbackData</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinsertextracreateparameter">FltInsertExtraCreateParameter</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltremoveextracreateparameter">FltRemoveExtraCreateParameter</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetecplistintocallbackdata">FltSetEcpListIntoCallbackData</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex">IoCreateFileEx</a>
