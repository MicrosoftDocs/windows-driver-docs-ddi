---
UID: NF:fltkernel.FltFindExtraCreateParameter
title: FltFindExtraCreateParameter function (fltkernel.h)
description: The FltFindExtraCreateParameter routine searches a given ECP list for an ECP context structure of a given type and returns a pointer to this structure if it is found.
old-location: ifsk\fltfindextracreateparameter.htm
tech.root: ifsk
ms.assetid: bfa38f16-55cf-40a9-b271-65d784d5156e
ms.date: 04/16/2018
keywords: ["FltFindExtraCreateParameter function"]
ms.keywords: FltApiRef_e_to_o_6f7f8d49-a0b3-4a32-9a51-d31ab84baf8a.xml, FltFindExtraCreateParameter, FltFindExtraCreateParameter routine [Installable File System Drivers], fltkernel/FltFindExtraCreateParameter, ifsk.fltfindextracreateparameter
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
 - FltFindExtraCreateParameter
 - fltkernel/FltFindExtraCreateParameter
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltFindExtraCreateParameter
---

# FltFindExtraCreateParameter function


## -description

The <b>FltFindExtraCreateParameter</b> routine searches a given ECP list for an ECP context structure of a given type and returns a pointer to this structure if it is found.

## -parameters

### -param Filter 

[in]
Opaque filter pointer for the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.

### -param EcpList 

[in]
Pointer to the ECP list structure in which to search for the ECP context structure (given by the <i>EcpType</i> parameter).

### -param EcpType 

[in]
Pointer to a GUID that uniquely identifies each ECP context structure.  This GUID value is used by the <b>FltFindExtraCreateParamter</b> routine to determine if the ECP context structure exists in the ECP list (given by the <i>EcpList</i> parameter).

### -param EcpContext 

[out, optional]
Optional parameter that receives a pointer to the found ECP context structure.  If the ECP context structure is not found in the ECP list, <i>EcpContext</i> is set to <b>NULL</b>.  If <i>EcpContext</i> is set to <b>NULL</b> by the caller, the return value of this routine can be used to determine if the ECP context structure is in the ECP list.

### -param EcpContextSize 

[out, optional]
Optional parameter that receives the size, in bytes, of the found ECP context structure.  If the ECP context structure is not found in the ECP list, <i>EcpContextSize</i> is set to zero.

## -returns

<b>FltFindExtraCreateParameter</b> returns one of the following NTSTATUS values:

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
The ECP context structure (as specified by the <i>EcpType</i> parameter) was found in the ECP list (as specified by the <i>EcpList</i> parameter).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The ECP context structure (as specified by the <i>EcpType</i> parameter) was not found in the ECP list (as specified by the <i>EcpList</i> parameter).

</td>
</tr>
</table>

## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff540148(v=vs.85)">ECP_LIST</a>



<b>FltAllocateExtraCreateParameterFromLookasideList</b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefileex2">FltCreateFileEx2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreeextracreateparameter">FltFreeExtraCreateParameter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetecplistfromcallbackdata">FltGetEcpListFromCallbackData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinsertextracreateparameter">FltInsertExtraCreateParameter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltremoveextracreateparameter">FltRemoveExtraCreateParameter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetecplistintocallbackdata">FltSetEcpListIntoCallbackData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex">IoCreateFileEx</a>

