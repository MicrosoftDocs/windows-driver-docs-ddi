---
UID: NF:fltkernel.FltGetNextExtraCreateParameter
title: FltGetNextExtraCreateParameter function
description: The FltGetNextExtraCreateParameter routine returns a pointer to the next (or first) extra create parameter context structure (ECP) in a given ECP list.
old-location: ifsk\fltgetnextextracreateparameter.htm
tech.root: ifsk
ms.assetid: 8eae5ac8-9da5-475f-8fbb-5e118bad4e67
ms.date: 04/16/2018
ms.keywords: FltApiRef_e_to_o_c458316b-2dd7-4ff2-a59f-a6dfbd659f47.xml, FltGetNextExtraCreateParameter, FltGetNextExtraCreateParameter routine [Installable File System Drivers], fltkernel/FltGetNextExtraCreateParameter, ifsk.fltgetnextextracreateparameter
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
-	FltGetNextExtraCreateParameter
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltGetNextExtraCreateParameter function


## -description


The <b>FltGetNextExtraCreateParameter</b> routine returns a pointer to the next (or first) extra create parameter context structure (ECP) in a given ECP list.


## -parameters




### -param Filter [in]

Opaque filter pointer to the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.


### -param EcpList [in]

Pointer to the ECP list to examine.


### -param CurrentEcpContext [in, optional]

Optional pointer to an ECP in the given ECP list.  If present, <b>FltGetNextExtraCreateParameter</b> returns the ECP after the <i>CurrentEcpContext</i> ECP.  If <i>CurrentEcpContext</i> is <b>NULL</b>, <b>FltGetNextExtraCreateParameter</b> returns the first ECP in the list.


### -param NextEcpType [out, optional]

Optional parameter that receives a pointer to the GUID of the returned ECP.


### -param NextEcpContext [out, optional]

Optional parameter that receives a pointer to the returned ECP.


### -param NextEcpContextSize [out, optional]

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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541728">FltAllocateExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541734">FltAllocateExtraCreateParameterFromLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541741">FltAllocateExtraCreateParameterList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541939">FltCreateFileEx2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542957">FltFreeExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542964">FltFreeExtraCreateParameterList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543016">FltGetEcpListFromCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543305">FltInsertExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544339">FltRemoveExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544510">FltSetEcpListIntoCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548283">IoCreateFileEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565392">Using GUIDs in Drivers</a>
 

 

