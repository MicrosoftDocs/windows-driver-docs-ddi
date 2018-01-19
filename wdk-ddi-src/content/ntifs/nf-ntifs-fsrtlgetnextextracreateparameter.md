---
UID: NF:ntifs.FsRtlGetNextExtraCreateParameter
title: FsRtlGetNextExtraCreateParameter function
author: windows-driver-content
description: The FsRtlGetNextExtraCreateParameter routine returns a pointer to the next (or first) extra create parameter (ECP) context structure in a given ECP list.
old-location: ifsk\fsrtlgetnextextracreateparameter.htm
old-project: ifsk
ms.assetid: b9dd2890-4b2d-4fe1-88bb-30d94ff36c44
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlGetNextExtraCreateParameter
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
req.alt-api: FsRtlGetNextExtraCreateParameter
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
req.typenames: TOKEN_TYPE
---

# FsRtlGetNextExtraCreateParameter function



## -description
The <b>FsRtlGetNextExtraCreateParameter</b> routine returns a pointer to the next (or first) extra create parameter (ECP) context structure  in a given ECP list.



## -syntax

````
NTSTATUS FsRtlGetNextExtraCreateParameter(
  _In_      PECP_LIST EcpList,
  _In_opt_  PVOID     CurrentEcpContext,
  _Out_opt_ LPGUID    NextEcpType,
  _Out_     PVOID     *NextEcpContext,
  _Out_opt_ ULONG     *NextEcpContextSize
);
````


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
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><b>FsRtlGetNextExtraCreateParameter </b>found an ECP context structure in the <i>EcpList</i> ECP list.
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>The <i>EcpList</i> ECP list is empty or <i>CurrentEcpContext</i> is the last ECP in the list (that is, there is no next ECP list element).  Additionally, <i>NextEcpContext</i> is set to <b>NULL</b> and <i>NextEcpContextSize</i> is set to zero.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The <i>EcpList</i> parameter is <b>NULL</b>.

 


## -remarks
The<b>FsRtlGetNextExtraCreateParameter</b> routine processes an ECP list in a non-circular manner.  That is, if the ECP context structure pointed to by the <i>CurrentEcpContext</i> parameter is the last element in the ECP list, there is no "next" ECP in the list and the routine returns STATUS_NOT_FOUND.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameter.md">FltAllocateExtraCreateParameter</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterfromlookasidelist.md">FltAllocateExtraCreateParameterFromLookasideList</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterlist.md">FltAllocateExtraCreateParameterList</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameter.md">FltFreeExtraCreateParameter</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameterlist.md">FltFreeExtraCreateParameterList</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetecplistfromcallbackdata.md">FltGetEcpListFromCallbackData</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltinsertextracreateparameter.md">FltInsertExtraCreateParameter</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltremoveextracreateparameter.md">FltRemoveExtraCreateParameter</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsetecplistintocallbackdata.md">FltSetEcpListIntoCallbackData</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlGetNextExtraCreateParameter routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

