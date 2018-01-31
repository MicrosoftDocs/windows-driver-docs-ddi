---
UID: NF:fltkernel.FltFindExtraCreateParameter
title: FltFindExtraCreateParameter function
author: windows-driver-content
description: The FltFindExtraCreateParameter routine searches a given ECP list for an ECP context structure of a given type and returns a pointer to this structure if it is found.
old-location: ifsk\fltfindextracreateparameter.htm
old-project: ifsk
ms.assetid: bfa38f16-55cf-40a9-b271-65d784d5156e
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.fltfindextracreateparameter, FltApiRef_e_to_o_6f7f8d49-a0b3-4a32-9a51-d31ab84baf8a.xml, FltFindExtraCreateParameter routine [Installable File System Drivers], FltFindExtraCreateParameter, fltkernel/FltFindExtraCreateParameter
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltFindExtraCreateParameter
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltFindExtraCreateParameter function


## -description


The <b>FltFindExtraCreateParameter</b> routine searches a given ECP list for an ECP context structure of a given type and returns a pointer to this structure if it is found.


## -syntax


````
NTSTATUS FltFindExtraCreateParameter(
  _In_      PFLT_FILTER Filter,
  _In_      PECP_LIST   EcpList,
  _In_      LPCGUID     EcpType,
  _Out_opt_ PVOID       *EcpContext,
  _Out_opt_ ULONG       *EcpContextSize
);
````


## -parameters




#### - Filter [in]

Opaque filter pointer for the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.


#### - EcpList [in]

Pointer to the ECP list structure in which to search for the ECP context structure (given by the <i>EcpType</i> parameter).


#### - EcpType [in]

Pointer to a GUID that uniquely identifies each ECP context structure.  This GUID value is used by the <b>FltFindExtraCreateParamter</b> routine to determine if the ECP context structure exists in the ECP list (given by the <i>EcpList</i> parameter).


#### - EcpContext [out, optional]

Optional parameter that receives a pointer to the found ECP context structure.  If the ECP context structure is not found in the ECP list, <i>EcpContext</i> is set to <b>NULL</b>.  If <i>EcpContext</i> is set to <b>NULL</b> by the caller, the return value of this routine can be used to determine if the ECP context structure is in the ECP list.


#### - EcpContextSize [out, optional]

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

<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameter.md">FltFreeExtraCreateParameter</a>

<a href="..\fltkernel\nf-fltkernel-fltgetecplistfromcallbackdata.md">FltGetEcpListFromCallbackData</a>

<b>FltAllocateExtraCreateParameterFromLookasideList</b>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>

<a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a>

<a href="..\fltkernel\nf-fltkernel-fltremoveextracreateparameter.md">FltRemoveExtraCreateParameter</a>

<a href="..\fltkernel\nf-fltkernel-fltinsertextracreateparameter.md">FltInsertExtraCreateParameter</a>

<a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a>

<a href="..\fltkernel\nf-fltkernel-fltsetecplistintocallbackdata.md">FltSetEcpListIntoCallbackData</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltFindExtraCreateParameter routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

