---
UID: NF:fltkernel.FltGetEcpListFromCallbackData
title: FltGetEcpListFromCallbackData function (fltkernel.h)
description: The FltGetEcpListFromCallbackData routine returns a pointer to an extra create parameter context structure (ECP) list that is associated with a given create operation callback-data object.
old-location: ifsk\fltgetecplistfromcallbackdata.htm
tech.root: ifsk
ms.assetid: 4e172b98-81f8-4e20-a622-232378114cf3
ms.date: 04/16/2018
ms.keywords: FltApiRef_e_to_o_781f52ec-4262-4205-81bb-2a0e824f50af.xml, FltGetEcpListFromCallbackData, FltGetEcpListFromCallbackData routine [Installable File System Drivers], fltkernel/FltGetEcpListFromCallbackData, ifsk.fltgetecplistfromcallbackdata
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltGetEcpListFromCallbackData
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltGetEcpListFromCallbackData function


## -description


The <b>FltGetEcpListFromCallbackData </b>routine returns a pointer to an extra create parameter context structure (ECP) list that is associated with a given create operation callback-data object.


## -parameters




### -param Filter [in]

An opaque filter pointer to the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.


### -param CallbackData

<p>A pointer to a callback-data object of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_callback_data"><b>FLT_CALLBACK_DATA</b></a>, which represents the create operation.</p>


### -param EcpList [out]

Receives a pointer to the ECP list that is associated with the <i>CallbackData</i> callback-data object.


## -returns



<b>FltGetEcpListFromCallbackData </b>returns one of the following NTSTATUS values:

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
<i>EcpList</i> received a pointer to the ECP list that is associated with the given callback-data object. If the callback-data object has no associated ECP, STATUS_SUCCESS is returned and <i>EcpList </i>is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The given callback-data object was not an IRP-based create operation.  In this case, <i>EcpList</i> is undefined.

</td>
</tr>
</table>
 




## -remarks



To attach an ECP list to a callback-data object, use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltsetecplistintocallbackdata">FltSetEcpListIntoCallbackData</a> routine.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff540148(v=vs.85)">ECP_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltacknowledgeecp">FltAcknowledgeEcp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltallocateextracreateparameter">FltAllocateExtraCreateParameter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltallocateextracreateparameterfromlookasidelist">FltAllocateExtraCreateParameterFromLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltallocateextracreateparameterlist">FltAllocateExtraCreateParameterList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcreatefileex2">FltCreateFileEx2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltdeleteextracreateparameterlookasidelist">FltDeleteExtraCreateParameterLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltfindextracreateparameter">FltFindExtraCreateParameter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltfreeextracreateparameter">FltFreeExtraCreateParameter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltfreeextracreateparameterlist">FltFreeExtraCreateParameterList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltgetnextextracreateparameter">FltGetNextExtraCreateParameter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltinitextracreateparameterlookasidelist">FltInitExtraCreateParameterLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltinsertextracreateparameter">FltInsertExtraCreateParameter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltisecpacknowledged">FltIsEcpAcknowledged</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltisecpfromusermode">FltIsEcpFromUserMode</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltremoveextracreateparameter">FltRemoveExtraCreateParameter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltsetecplistintocallbackdata">FltSetEcpListIntoCallbackData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-iocreatefileex">IoCreateFileEx</a>
 

 

