---
UID: NF:fltkernel.FltGetNextExtraCreateParameter
title: FltGetNextExtraCreateParameter function (fltkernel.h)
description: The FltGetNextExtraCreateParameter routine returns a pointer to the next (or first) extra create parameter context structure (ECP) in a given ECP list.
old-location: ifsk\fltgetnextextracreateparameter.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FltGetNextExtraCreateParameter function"]
ms.keywords: FltApiRef_e_to_o_c458316b-2dd7-4ff2-a59f-a6dfbd659f47.xml, FltGetNextExtraCreateParameter, FltGetNextExtraCreateParameter routine [Installable File System Drivers], fltkernel/FltGetNextExtraCreateParameter, ifsk.fltgetnextextracreateparameter
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available starting with Windows Vista.
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltGetNextExtraCreateParameter
 - fltkernel/FltGetNextExtraCreateParameter
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltGetNextExtraCreateParameter
---

# FltGetNextExtraCreateParameter function


## -description

The <b>FltGetNextExtraCreateParameter</b> routine returns a pointer to the next (or first) extra create parameter context structure (ECP) in a given ECP list.

## -parameters

### -param Filter 

[in]
Opaque filter pointer to the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.

### -param EcpList 

[in]
Pointer to the ECP list to examine.

### -param CurrentEcpContext 

[in, optional]
Optional pointer to an ECP in the given ECP list.  If present, <b>FltGetNextExtraCreateParameter</b> returns the ECP after the <i>CurrentEcpContext</i> ECP.  If <i>CurrentEcpContext</i> is <b>NULL</b>, <b>FltGetNextExtraCreateParameter</b> returns the first ECP in the list.

### -param NextEcpType 

[out, optional]
Optional parameter that receives a pointer to the GUID of the returned ECP.

### -param NextEcpContext 

[out, optional]
Optional parameter that receives a pointer to the returned ECP.

### -param NextEcpContextSize 

[out, optional]
Optional parameter that receives the size, in bytes, of the returned ECP.

## -returns

<b>FltGetNextExtraCreateParameter</b> returns one of the following NTSTATUS values:

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
An ECP was found in the <i>EcpList</i> ECP list.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The <i>EcpList</i> ECP list is empty or <i>CurrentEcpContext</i> is the last ECP in the list that is, there is no next ECP list element).  Additionally, <i>NextEcpContext</i> is set to <b>NULL</b> and <i>NextEcpContextSize</i> is set to zero.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>EcpList</i> parameter is <b>NULL</b>.

</td>
</tr>
</table>

## -remarks

This routine is available starting with Windows Vista. 

The<b>FltGetNextExtraCreateParameter</b> routine processes an ECP list in a non-circular manner.  That is, if the ECP pointed to by the <i>CurrentEcpContext</i> parameter is the last ECP element in the ECP list, there is no "next" ECP in the list and the routine returns STATUS_NOT_FOUND.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/ff540148(v=vs.85)">ECP_LIST</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocateextracreateparameter">FltAllocateExtraCreateParameter</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocateextracreateparameterfromlookasidelist">FltAllocateExtraCreateParameterFromLookasideList</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocateextracreateparameterlist">FltAllocateExtraCreateParameterList</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefileex2">FltCreateFileEx2</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreeextracreateparameter">FltFreeExtraCreateParameter</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreeextracreateparameterlist">FltFreeExtraCreateParameterList</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetecplistfromcallbackdata">FltGetEcpListFromCallbackData</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinsertextracreateparameter">FltInsertExtraCreateParameter</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltremoveextracreateparameter">FltRemoveExtraCreateParameter</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetecplistintocallbackdata">FltSetEcpListIntoCallbackData</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex">IoCreateFileEx</a>



<a href="/windows-hardware/drivers/kernel/using-guids-in-drivers">Using GUIDs in Drivers</a>
