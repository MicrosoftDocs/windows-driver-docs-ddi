---
UID: NF:ntifs.FsRtlGetNextExtraCreateParameter
title: FsRtlGetNextExtraCreateParameter function
author: windows-driver-content
description: The FsRtlGetNextExtraCreateParameter routine returns a pointer to the next (or first) extra create parameter (ECP) context structure in a given ECP list.
old-location: ifsk\fsrtlgetnextextracreateparameter.htm
old-project: ifsk
ms.assetid: b9dd2890-4b2d-4fe1-88bb-30d94ff36c44
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FsRtlGetNextExtraCreateParameter, FsRtlGetNextExtraCreateParameter routine [Installable File System Drivers], fsrtlref_096516d0-6888-4dfa-98b3-b7b67794bf08.xml, ifsk.fsrtlgetnextextracreateparameter, ntifs/FsRtlGetNextExtraCreateParameter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlGetNextExtraCreateParameter routine is available starting with Windows Vista.
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlGetNextExtraCreateParameter
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlGetNextExtraCreateParameter function


## -description


The <b>FsRtlGetNextExtraCreateParameter</b> routine returns a pointer to the next (or first) extra create parameter (ECP) context structure  in a given ECP list.


## -parameters




### -param EcpList [in]

Pointer to the ECP list to examine.


### -param CurrentEcpContext [in, optional]

Optional pointer to an ECP context structure in the given ECP list.  If present, <b>FsRtlGetNextExtraCreateParameter</b> returns a pointer to the ECP after the <i>CurrentEcpContext</i> ECP context structure.  If <i>CurrentEcpContext</i> is <b>NULL</b>, <b>FsRtlGetNextExtraCreateParameter</b> returns the first ECP context structure in the list.


### -param NextEcpType [out, optional]

Optional parameter that receives a pointer to the GUID of the returned ECP context structure.


### -param NextEcpContext [out]

Optional parameter that receives a pointer to the returned ECP context structure.


### -param NextEcpContextSize [out, optional]

Optional parameter that receives the size, in bytes, of the returned ECP context structure.


## -returns



<b>FsRtlGetNextExtraCreateParameter</b> returns one of the following NTSTATUS values:

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
<b>FsRtlGetNextExtraCreateParameter </b>found an ECP context structure in the <i>EcpList</i> ECP list.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The <i>EcpList</i> ECP list is empty or <i>CurrentEcpContext</i> is the last ECP in the list (that is, there is no next ECP list element).  Additionally, <i>NextEcpContext</i> is set to <b>NULL</b> and <i>NextEcpContextSize</i> is set to zero.

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



The<b>FsRtlGetNextExtraCreateParameter</b> routine processes an ECP list in a non-circular manner.  That is, if the ECP context structure pointed to by the <i>CurrentEcpContext</i> parameter is the last element in the ECP list, there is no "next" ECP in the list and the routine returns STATUS_NOT_FOUND.




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
 

 

