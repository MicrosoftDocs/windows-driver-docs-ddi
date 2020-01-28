---
UID: NF:fltkernel.FltRemoveExtraCreateParameter
title: FltRemoveExtraCreateParameter function (fltkernel.h)
description: The FltRemoveExtraCreateParameter routine searches an ECP list for an ECP context structure and, if found, detaches it from the ECP list.
old-location: ifsk\fltremoveextracreateparameter.htm
tech.root: ifsk
ms.assetid: 924e9108-f0cf-4202-905c-04a27c15dfa3
ms.date: 04/16/2018
ms.keywords: FltApiRef_p_to_z_696787f2-1381-451f-aed4-bf307ee58291.xml, FltRemoveExtraCreateParameter, FltRemoveExtraCreateParameter routine [Installable File System Drivers], fltkernel/FltRemoveExtraCreateParameter, ifsk.fltremoveextracreateparameter
f1_keywords:
 - "fltkernel/FltRemoveExtraCreateParameter"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltRemoveExtraCreateParameter
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltRemoveExtraCreateParameter function


## -description


The <b>FltRemoveExtraCreateParameter</b> routine searches an ECP list for an ECP context structure and, if found, detaches it from the ECP list.


## -parameters




### -param Filter [in]

Opaque filter pointer for the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.


### -param EcpList [in, out]

Pointer to the extra create parameter (ECP) list that contains the ECP context structure to be detached from the given list.


### -param EcpType [in]

Pointer to a user-defined GUID that uniquely identifies the ECP context structure to be detached from the list.


### -param EcpContext [out]

Pointer to the detached ECP context structure.  If the ECP context structure is successfully detached from the given list, this parameter will be set to point to the detached ECP context structure.  If the ECP context structure is not found in the given ECP list, this parameter is set to <b>NULL</b>.


### -param EcpContextSize [out, optional]

Optional parameter that receives the size of the detached ECP context structure.  If this parameter is present when the routine is called, the parameter will receive the size, in bytes, of the detached ECP context structure.  If the given ECP context structure was not found in the given ECP list, this parameter is undefined. 


## -returns



<b>FltRemoveExtraCreateParameter</b> returns one of the following NTSTATUS values:

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
The given ECP context structure was successfully detached from the given ECP list.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The given ECP context structure was not found in the given ECP list.

</td>
</tr>
</table>
 




## -remarks



The <b>FltRemoveExtraCreateParameter</b> routine searches the ECP list given by the <i>EcpList</i> parameter for an ECP context structure given by the <i>EcpType</i> parameter.  If the ECP context structure exists in the list, it is detached from the list, the <i>EcpContext</i> parameter is set to point to it, and the routine returns STATUS_SUCCESS. If the ECP context structure does not exist in the list, the <i>EcpContext</i> parameter is set to <b>NULL</b> and the routine returns STATUS_NOT_FOUND.


<div class="alert"><b>Note</b>  This routine does not free the memory pool for the ECP context structure.  To free the ECP context structure, first call this routine to detach it from the list and then call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreeextracreateparameter">FltFreeExtraCreateParameter</a> routine to free the ECP context structure itself.</div>
<div> </div>





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
 

 

