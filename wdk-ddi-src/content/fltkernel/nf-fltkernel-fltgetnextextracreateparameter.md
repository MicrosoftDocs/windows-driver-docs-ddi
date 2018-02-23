---
UID: NF:fltkernel.FltGetNextExtraCreateParameter
title: FltGetNextExtraCreateParameter function
author: windows-driver-content
description: The FltGetNextExtraCreateParameter routine returns a pointer to the next (or first) extra create parameter context structure (ECP) in a given ECP list.
old-location: ifsk\fltgetnextextracreateparameter.htm
old-project: ifsk
ms.assetid: 8eae5ac8-9da5-475f-8fbb-5e118bad4e67
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_e_to_o_c458316b-2dd7-4ff2-a59f-a6dfbd659f47.xml, FltGetNextExtraCreateParameter routine [Installable File System Drivers], ifsk.fltgetnextextracreateparameter, fltkernel/FltGetNextExtraCreateParameter, FltGetNextExtraCreateParameter
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
-	FltGetNextExtraCreateParameter
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltGetNextExtraCreateParameter function


## -description


The <b>FltGetNextExtraCreateParameter</b> routine returns a pointer to the next (or first) extra create parameter context structure (ECP) in a given ECP list.


## -syntax


````
NTSTATUS FltGetNextExtraCreateParameter(
  _In_      PFLT_FILTER Filter,
  _In_      PECP_LIST   EcpList,
  _In_opt_  PVOID       CurrentEcpContext,
  _Out_opt_ LPGUID      NextEcpType,
  _Out_opt_ PVOID       *NextEcpContext,
  _Out_opt_ ULONG       *NextEcpContextSize
);
````


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

<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterlist.md">FltAllocateExtraCreateParameterList</a>



<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameterlist.md">FltFreeExtraCreateParameterList</a>



<a href="..\fltkernel\nf-fltkernel-fltinsertextracreateparameter.md">FltInsertExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



<a href="..\fltkernel\nf-fltkernel-fltremoveextracreateparameter.md">FltRemoveExtraCreateParameter</a>



<a href="..\fltkernel\nf-fltkernel-fltgetecplistfromcallbackdata.md">FltGetEcpListFromCallbackData</a>



<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameter.md">FltAllocateExtraCreateParameter</a>



<a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a>



<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterfromlookasidelist.md">FltAllocateExtraCreateParameterFromLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565392">Using GUIDs in Drivers</a>



<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameterlist.md">FltFreeExtraCreateParameterList</a>



<a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a>



<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameter.md">FltFreeExtraCreateParameter</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetNextExtraCreateParameter routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

