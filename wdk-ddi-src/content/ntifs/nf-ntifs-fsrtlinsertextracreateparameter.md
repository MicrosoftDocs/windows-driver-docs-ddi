---
UID: NF:ntifs.FsRtlInsertExtraCreateParameter
title: FsRtlInsertExtraCreateParameter function (ntifs.h)
description: The FsRtlInsertExtraCreateParameter routine inserts an extra create parameter (ECP) context structure into an ECP list.
old-location: ifsk\fsrtlinsertextracreateparameter.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FsRtlInsertExtraCreateParameter function"]
ms.keywords: FsRtlInsertExtraCreateParameter, FsRtlInsertExtraCreateParameter routine [Installable File System Drivers], fsrtlref_25aa9ff1-4921-4f96-98dc-04230d450e98.xml, ifsk.fsrtlinsertextracreateparameter, ntifs/FsRtlInsertExtraCreateParameter
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FltInsertExtraCreateParameter routine is available starting with Windows Vista.
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
 - FsRtlInsertExtraCreateParameter
 - ntifs/FsRtlInsertExtraCreateParameter
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlInsertExtraCreateParameter
---

# FsRtlInsertExtraCreateParameter function


## -description

The <b>FsRtlInsertExtraCreateParameter</b> routine inserts an extra create parameter (ECP) context structure into an ECP list.

## -parameters

### -param EcpList [in, out]


Pointer to the ECP list structure to which the ECP context structure, pointed to by the <i>EcpContext</i> parameter, should be added.

### -param EcpContext [in, out]


Pointer to the ECP context structure to be added to the ECP list, pointed to by the <i>EcpList</i> parameter.

## -returns

<b>FsRtlInsertExtraCreateParameter</b> returns one of the following NTSTATUS values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The given ECP context structure was successfully inserted into the given ECP list.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The given ECP context structure already exists in the given ECP list.  In the context of ECP list insertion, two ECP context structures are considered to be identical if they contain equal GUID values.

</td>
</tr>
</table>

## -remarks

The <b>FsRtlInsertExtraCreateParameter</b> routine assumes that the given ECP context structure to be inserted into the given ECP list was previously allocated by the <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocateextracreateparameter">FltAllocateExtraCreateParameter</a> routine.

Each ECP context structure inserted into the ECP list must have a unique GUID value. This unique value is set when the ECP context structure is allocated by the <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocateextracreateparameter">FltAllocateExtraCreateParameter</a> routine.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/ff540148(v=vs.85)">ECP_LIST</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocateextracreateparameter">FltAllocateExtraCreateParameter</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocateextracreateparameterfromlookasidelist">FltAllocateExtraCreateParameterFromLookasideList</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocateextracreateparameterlist">FltAllocateExtraCreateParameterList</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefileex2">FltCreateFileEx2</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreeextracreateparameter">FltFreeExtraCreateParameter</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetecplistfromcallbackdata">FltGetEcpListFromCallbackData</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltremoveextracreateparameter">FltRemoveExtraCreateParameter</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetecplistintocallbackdata">FltSetEcpListIntoCallbackData</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex">IoCreateFileEx</a>
