---
UID: NF:fltkernel.FltGetEcpListFromCallbackData
title: FltGetEcpListFromCallbackData function
author: windows-driver-content
description: The FltGetEcpListFromCallbackData routine returns a pointer to an extra create parameter context structure (ECP) list that is associated with a given create operation callback-data object.
old-location: ifsk\fltgetecplistfromcallbackdata.htm
tech.root: ifsk
ms.assetid: 4e172b98-81f8-4e20-a622-232378114cf3
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltApiRef_e_to_o_781f52ec-4262-4205-81bb-2a0e824f50af.xml, FltGetEcpListFromCallbackData, FltGetEcpListFromCallbackData routine [Installable File System Drivers], fltkernel/FltGetEcpListFromCallbackData, ifsk.fltgetecplistfromcallbackdata
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltGetEcpListFromCallbackData
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

TBD


### -param EcpList [out]

Receives a pointer to the ECP list that is associated with the <i>Data</i> callback-data object.


#### - Data [in]

A pointer to a callback-data object of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>, which represents the create operation.


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



To attach an ECP list to a callback-data object, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544510">FltSetEcpListIntoCallbackData</a> routine.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541661">FltAcknowledgeEcp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541728">FltAllocateExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541734">FltAllocateExtraCreateParameterFromLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541741">FltAllocateExtraCreateParameterList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541939">FltCreateFileEx2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541973">FltDeleteExtraCreateParameterLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542094">FltFindExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542957">FltFreeExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542964">FltFreeExtraCreateParameterList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543104">FltGetNextExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543261">FltInitExtraCreateParameterLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543305">FltInsertExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543321">FltIsEcpAcknowledged</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543325">FltIsEcpFromUserMode</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544339">FltRemoveExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544510">FltSetEcpListIntoCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548283">IoCreateFileEx</a>
 

 

