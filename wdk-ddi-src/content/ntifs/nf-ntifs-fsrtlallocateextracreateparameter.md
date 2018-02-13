---
UID: NF:ntifs.FsRtlAllocateExtraCreateParameter
title: FsRtlAllocateExtraCreateParameter function
author: windows-driver-content
description: The FsRtlAllocateExtraCreateParameter routine allocates memory for a user-defined extra create parameter (ECP) context structure and generates a pointer to that structure.
old-location: ifsk\fsrtlallocateextracreateparameter.htm
old-project: ifsk
ms.assetid: 644680a9-ec56-4d65-890f-fbc11badf2b7
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: FsRtlAllocateExtraCreateParameter routine [Installable File System Drivers], ifsk.fsrtlallocateextracreateparameter, fsrtlref_97f1c552-b822-4fda-9327-8d127f42080b.xml, FsRtlAllocateExtraCreateParameter, ntifs/FsRtlAllocateExtraCreateParameter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlAllocateExtraCreateParameter routine is available starting with Windows Vista.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FsRtlAllocateExtraCreateParameter
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlAllocateExtraCreateParameter function


## -description


The <b>FsRtlAllocateExtraCreateParameter</b> routine allocates memory for a user-defined extra create parameter (ECP) context structure and generates a pointer to that structure.


## -syntax


````
NTSTATUS FsRtlAllocateExtraCreateParameter(
  _In_     LPCGUID                                        EcpType,
  _In_     ULONG                                          SizeOfContext,
  _In_     FSRTL_ALLOCATE_ECP_FLAGS                       Flags,
  _In_opt_ PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK CleanupCallback,
  _In_     ULONG                                          PoolTag,
  _Out_    PVOID                                          *EcpContext
);
````


## -parameters




### -param EcpType [in]

A pointer to a user-defined GUID that indicates the type of the ECP context structure.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff565392">Using GUIDs in Drivers</a> for more information.


### -param SizeOfContext [in]

The size, in bytes, of the user-defined context structure.


### -param Flags [in]

Defines pool allocation options.  The following describes how pool will be allocated when one or more of the listed flag values are combined with the <i>Flags</i> parameter by using a bitwise OR operation:  

<ul>
<li>
FSRTL_ALLOCATE_ECP_FLAG_NONPAGED_POOL - Non-paged pool will be allocated.  If this flag value is not used, paged pool will be allocated.

</li>
<li>
FSRTL_ALLOCATE_ECPLIST_FLAG_CHARGE_QUOTA - All pool allocated by <b>FsRtlAllocateExtraCreateParameter</b> will be charged against the current process' memory quota.

</li>
</ul>
If more than one flag is used, all of the effects associated with the utilized flag values will occur.


### -param CleanupCallback [in, optional]

Optional pointer to a filter-defined cleanup callback routine of type <a href="..\ntifs\nc-ntifs-pfsrtl_extra_create_parameter_cleanup_callback.md">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a>.  The cleanup callback routine is called when the ECP structure (created by the <b>FsRtlAllocateExtraCreateParameter</b> routine) is deleted.  Set this parameter to <b>NULL</b> if a cleanup callback routine is not applicable.


### -param PoolTag [in]

Specifies the pool tag for the allocated memory. For more information, see the <i>Tag</i> parameter of <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>.


### -param EcpContext [out]

Receives a pointer to the allocated ECP context structure.  If the routine failed to allocate sufficient pool, the value pointed to by <i>EcpContext </i>will be <b>NULL</b> and <b>FsRtlAllocateExtraCreateParameter</b> will return status code STATUS_INSUFFICIENT_RESOURCES.


## -returns



FltAllocateExtraCreateParameter can return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>FsRtlAllocateExtraCreateParameter</b> was unable to allocate sufficient memory for an ECP structure.  In this case, <i>EcpContext </i>is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The ECP structure was successfully allocated.  In this case, a pointer to the allocated structure is returned in the <i>EcpContext </i> parameter.

</td>
</tr>
</table>
 




## -remarks



By default, the <b>FsRtlAllocateExtraCreateParameter</b> routine allocates paged memory pool for a user-defined ECP context structure.  If the FSRTL_ALLOCATE_ECP_FLAG_NONPAGED_POOL bitmask is used as described in the <i>Flags</i> parameter, a non-paged memory pool is allocated.  After this pool has been allocated and the ECP context structure has been initialized, the <a href="..\fltkernel\nf-fltkernel-fltinsertextracreateparameter.md">FltInsertExtraCreateParameter</a> routine is used to insert the ECP context structure (ECP list element) into an ECP list structure (<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>).

If the caller allocates ECP_LIST and one or more ECPs are used in a call to <a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a>, the previous description is correct. In this case, the system does not free any of the ECPs, so the caller can make multiple calls to <b>IoCreateFileEx</b> with the same ECP set. However, if a file system or file system filter driver attaches an ECP to an existing or newly-created ECP_LIST while processing an IRP_MJ_CREATE request, this ECP is automatically cleaned up when the IRP completes. As a result, a filter driver does not have to clean up ECPs that are added dynamically. This allows a filter driver's ECP to be properly propagated across the reparse points--a process that can require multiple IRP_MJ_CREATE requests to be generated.




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameter.md">FltFreeExtraCreateParameter</a>



<a href="..\ntifs\nc-ntifs-pfsrtl_extra_create_parameter_cleanup_callback.md">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a>



<a href="..\fltkernel\nf-fltkernel-fltsetecplistintocallbackdata.md">FltSetEcpListIntoCallbackData</a>



<a href="..\fltkernel\nf-fltkernel-fltremoveextracreateparameter.md">FltRemoveExtraCreateParameter</a>



<a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a>



<a href="..\fltkernel\nf-fltkernel-fltgetecplistfromcallbackdata.md">FltGetEcpListFromCallbackData</a>



<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterlist.md">FltAllocateExtraCreateParameterList</a>



<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterfromlookasidelist.md">FltAllocateExtraCreateParameterFromLookasideList</a>



<a href="..\fltkernel\nf-fltkernel-fltinsertextracreateparameter.md">FltInsertExtraCreateParameter</a>



<a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a>



<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameterlist.md">FltFreeExtraCreateParameterList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlAllocateExtraCreateParameter routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

