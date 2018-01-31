---
UID: NF:fltkernel.FltAllocateExtraCreateParameter
title: FltAllocateExtraCreateParameter function
author: windows-driver-content
description: The FltAllocateExtraCreateParameter routine allocates paged memory pool for a user-defined extra create parameter (ECP) context structure and generates a pointer to that structure.
old-location: ifsk\fltallocateextracreateparameter.htm
old-project: ifsk
ms.assetid: 85751db5-7a73-4aa5-baf8-0173e9a8f495
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.fltallocateextracreateparameter, FltAllocateExtraCreateParameter routine [Installable File System Drivers], FltApiRef_a_to_d_937e6c81-7251-4f94-a868-88f65e219c73.xml, fltkernel/FltAllocateExtraCreateParameter, FltAllocateExtraCreateParameter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.dll: 
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	FltMgr.lib
-	FltMgr.dll
apiname:
-	FltAllocateExtraCreateParameter
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltAllocateExtraCreateParameter function


## -description


The <b>FltAllocateExtraCreateParameter</b> routine allocates paged memory pool for a user-defined extra create parameter (ECP) context structure and generates a pointer to that structure.


## -syntax


````
NTSTATUS FltAllocateExtraCreateParameter(
  _In_     PFLT_FILTER                                    Filter,
  _In_     LPCGUID                                        EcpType,
  _In_     ULONG                                          SizeOfContext,
  _In_     FSRTL_ALLOCATE_ECP_FLAGS                       Flags,
  _In_opt_ PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK CleanupCallback,
  _In_     ULONG                                          PoolTag,
  _Out_    PVOID                                          *EcpContext
);
````


## -parameters




#### - Filter [in]

Opaque filter pointer for the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.


#### - EcpType [in]

Pointer to a user-defined GUID indicating the type of the ECP context structure.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff565392">Using GUIDs in Drivers</a> for more information.


#### - SizeOfContext [in]

The size, in bytes, of the user-defined context structure.


#### - Flags [in]

Defines pool allocation options.  The following describes how pool will be allocated when one or more of the listed flag values are combined with the <i>Flags</i> parameter by using a bitwise OR operation:  
<ul>
<li>
FSRTL_ALLOCATE_ECP_FLAG_NONPAGED_POOL - Non-paged pool will be allocated.  If this flag value is not used, paged pool will be allocated.

</li>
<li>
FSRTL_ALLOCATE_ECPLIST_FLAG_CHARGE_QUOTA - All pool allocated by this routine will be charged against the current process' memory quota.

</li>
</ul>If more than one flag is used, all of the effects associated with the utilized flag values will occur.


#### - CleanupCallback [in, optional]

Optional pointer to a minifilter-defined cleanup callback routine of type <a href="..\ntifs\nc-ntifs-pfsrtl_extra_create_parameter_cleanup_callback.md">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a>.  The cleanup callback routine is called when the ECP structure (created by the <b>FltAllocateExtraCreateParameter</b> routine) is deleted.  Set this parameter to <b>NULL</b> if a cleanup callback routine is not applicable.


#### - PoolTag [in]

Specifies the pool tag for the allocated memory. For more information, see the <i>Tag</i> parameter of <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>.


#### - EcpContext [out]

Receives a pointer to the allocated ECP context structure.  If the routine failed to allocate sufficient pool, <i>*EcpContext </i>will be <b>NULL</b> and the routine will return status code STATUS_INSUFFICIENT_RESOURCES.


## -returns


<b>FltAllocateExtraCreateParameter</b> can return one of the following values:
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
<b>FltAllocateExtraCreateParameter</b> was unable to allocate sufficient memory for an ECP structure.  In this case, <i>EcpContext </i>will be <b>NULL</b>.

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


The <b>FltAllocateExtraCreateParameter</b> routine is available starting with Windows Vista. 

By default, the <b>FltAllocateExtraCreateParameter</b> routine allocates paged memory pool for a user-defined ECP context structure.  If the FSRTL_ALLOCATE_ECP_FLAG_NONPAGED_POOL bitmask is used as described above, a non-paged memory pool is allocated.  Once this pool has been allocated and the ECP context structure has been initialized, the <a href="..\fltkernel\nf-fltkernel-fltinsertextracreateparameter.md">FltInsertExtraCreateParameter</a> routine is used to insert the ECP context structure (ECP list element) into an ECP list structure (ECP list).

Memory pool that is allocated by the <b>FltAllocateExtraCreateParameter</b> routine is not automatically freed by the operating system.  This memory pool must eventually be released by using one of the following methods:
<ul>
<li>
Call the <a href="..\fltkernel\nf-fltkernel-fltremoveextracreateparameter.md">FltRemoveExtraCreateParameter</a> routine to remove the ECP context structure from the ECP list and then call the <a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameter.md">FltFreeExtraCreateParameter</a> routine to free the ECP context structure itself.  The ECP list remains in existence.

</li>
<li>
Call the <a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameterlist.md">FltFreeExtraCreateParameterList</a> routine - this frees the ECP list including any list elements (ECP context structures).  The ECP list is destroyed.

</li>
</ul>


## -see-also

<a href="..\ntifs\nc-ntifs-pfsrtl_extra_create_parameter_cleanup_callback.md">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a>

<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameter.md">FltFreeExtraCreateParameter</a>

<a href="..\fltkernel\nf-fltkernel-fltgetecplistfromcallbackdata.md">FltGetEcpListFromCallbackData</a>

<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterfromlookasidelist.md">FltAllocateExtraCreateParameterFromLookasideList</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>

<a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a>

<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterlist.md">FltAllocateExtraCreateParameterList</a>

<a href="..\fltkernel\nf-fltkernel-fltremoveextracreateparameter.md">FltRemoveExtraCreateParameter</a>

<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameterlist.md">FltFreeExtraCreateParameterList</a>

<a href="..\fltkernel\nf-fltkernel-fltinsertextracreateparameter.md">FltInsertExtraCreateParameter</a>

<a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a>

<a href="..\fltkernel\nf-fltkernel-fltsetecplistintocallbackdata.md">FltSetEcpListIntoCallbackData</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltAllocateExtraCreateParameter routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

