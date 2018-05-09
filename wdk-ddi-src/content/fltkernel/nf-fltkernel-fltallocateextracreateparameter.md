---
UID: NF:fltkernel.FltAllocateExtraCreateParameter
title: FltAllocateExtraCreateParameter function
author: windows-driver-content
description: The FltAllocateExtraCreateParameter routine allocates paged memory pool for a user-defined extra create parameter (ECP) context structure and generates a pointer to that structure.
old-location: ifsk\fltallocateextracreateparameter.htm
old-project: ifsk
ms.assetid: 85751db5-7a73-4aa5-baf8-0173e9a8f495
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltAllocateExtraCreateParameter, FltAllocateExtraCreateParameter routine [Installable File System Drivers], FltApiRef_a_to_d_937e6c81-7251-4f94-a868-88f65e219c73.xml, fltkernel/FltAllocateExtraCreateParameter, ifsk.fltallocateextracreateparameter
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	FltMgr.lib
-	FltMgr.dll
api_name:
-	FltAllocateExtraCreateParameter
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltAllocateExtraCreateParameter function


## -description


The <b>FltAllocateExtraCreateParameter</b> routine allocates paged memory pool for a user-defined extra create parameter (ECP) context structure and generates a pointer to that structure.


## -parameters




### -param Filter [in]

Opaque filter pointer for the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.


### -param EcpType [in]

Pointer to a user-defined GUID indicating the type of the ECP context structure.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff565392">Using GUIDs in Drivers</a> for more information.


### -param SizeOfContext [in]

The size, in bytes, of the user-defined context structure.


### -param Flags [in]

Defines pool allocation options.  The following describes how pool will be allocated when one or more of the listed flag values are combined with the <i>Flags</i> parameter by using a bitwise OR operation:  

<ul>
<li>
FSRTL_ALLOCATE_ECP_FLAG_NONPAGED_POOL - Non-paged pool will be allocated.  If this flag value is not used, paged pool will be allocated.

</li>
<li>
FSRTL_ALLOCATE_ECPLIST_FLAG_CHARGE_QUOTA - All pool allocated by this routine will be charged against the current process' memory quota.

</li>
</ul>
If more than one flag is used, all of the effects associated with the utilized flag values will occur.


### -param CleanupCallback [in, optional]

Optional pointer to a minifilter-defined cleanup callback routine of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff551124">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a>.  The cleanup callback routine is called when the ECP structure (created by the <b>FltAllocateExtraCreateParameter</b> routine) is deleted.  Set this parameter to <b>NULL</b> if a cleanup callback routine is not applicable.


### -param PoolTag [in]

Specifies the pool tag for the allocated memory. For more information, see the <i>Tag</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a>.


### -param EcpContext [out]

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

By default, the <b>FltAllocateExtraCreateParameter</b> routine allocates paged memory pool for a user-defined ECP context structure.  If the FSRTL_ALLOCATE_ECP_FLAG_NONPAGED_POOL bitmask is used as described above, a non-paged memory pool is allocated.  Once this pool has been allocated and the ECP context structure has been initialized, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543305">FltInsertExtraCreateParameter</a> routine is used to insert the ECP context structure (ECP list element) into an ECP list structure (ECP list).

Memory pool that is allocated by the <b>FltAllocateExtraCreateParameter</b> routine is not automatically freed by the operating system.  This memory pool must eventually be released by using one of the following methods:

<ul>
<li>
Call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544339">FltRemoveExtraCreateParameter</a> routine to remove the ECP context structure from the ECP list and then call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542957">FltFreeExtraCreateParameter</a> routine to free the ECP context structure itself.  The ECP list remains in existence.

</li>
<li>
Call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542964">FltFreeExtraCreateParameterList</a> routine - this frees the ECP list including any list elements (ECP context structures).  The ECP list is destroyed.

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551124">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a>
 

 

