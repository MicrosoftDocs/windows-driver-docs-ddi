---
UID: NF:fltkernel.FltSetEcpListIntoCallbackData
title: FltSetEcpListIntoCallbackData function
author: windows-driver-content
description: The FltSetEcpListIntoCallbackData routine attaches an extra create parameter context structure (ECP) list to a create operation callback-data object.
old-location: ifsk\fltsetecplistintocallbackdata.htm
old-project: ifsk
ms.assetid: 91179c1c-fe45-418f-8992-a40e41e3017a
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltApiRef_p_to_z_01e8fac7-3c58-4ed2-85ac-38580cca36e6.xml, FltSetEcpListIntoCallbackData, FltSetEcpListIntoCallbackData routine [Installable File System Drivers], fltkernel/FltSetEcpListIntoCallbackData, ifsk.fltsetecplistintocallbackdata
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
-	FltSetEcpListIntoCallbackData
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltSetEcpListIntoCallbackData function


## -description


The <b>FltSetEcpListIntoCallbackData </b>routine attaches an extra create parameter context structure (ECP) list to a create operation callback-data object.


## -parameters




### -param Filter [in]

Opaque filter pointer to the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.


### -param CallbackData

TBD


### -param EcpList [in]

Pointer to the ECP list, which contains one or more ECPs, to be attached to the callback-data object.


#### - Data [in]

Pointer to a callback-data object of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>, which represents the create operation.


## -returns



<b>FltSetEcpListIntoCallbackData </b>returns one of the following NTSTATUS values:

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
The given ECP list was successfully attached to the given callback-data object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>
</td>
<td width="60%">
The given callback data object was not an IRP-based create operation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_3</b></dt>
</dl>
</td>
<td width="60%">
An ECP list has already been attached to the given callback-data object.

</td>
</tr>
</table>
 




## -remarks



The <b>FltSetEcpListIntoCallbackData</b> routine provides a mechanism for passing extra create parameters down the file system filter stack to underlying minifilter and legacy filter drivers.

To retrieve an attached ECP list from a given callback-data object, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543016">FltGetEcpListFromCallbackData</a> routine.




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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543016">FltGetEcpListFromCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543104">FltGetNextExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543261">FltInitExtraCreateParameterLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543305">FltInsertExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543321">FltIsEcpAcknowledged</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543325">FltIsEcpFromUserMode</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544339">FltRemoveExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548283">IoCreateFileEx</a>
 

 

