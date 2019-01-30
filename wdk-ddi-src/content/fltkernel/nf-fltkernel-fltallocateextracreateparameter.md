---
UID: NF:fltkernel.FltAllocateExtraCreateParameter
title: FltAllocateExtraCreateParameter function (fltkernel.h)
description: The FltAllocateExtraCreateParameter routine allocates paged memory pool for a user-defined extra create parameter (ECP) context structure and generates a pointer to that structure.
old-location: ifsk\fltallocateextracreateparameter.htm
tech.root: ifsk
ms.assetid: 85751db5-7a73-4aa5-baf8-0173e9a8f495
ms.date: 04/16/2018
ms.keywords: FltAllocateExtraCreateParameter, FltAllocateExtraCreateParameter routine [Installable File System Drivers], FltApiRef_a_to_d_937e6c81-7251-4f94-a868-88f65e219c73.xml, fltkernel/FltAllocateExtraCreateParameter, ifsk.fltallocateextracreateparameter
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

The **FltAllocateExtraCreateParameter** routine allocates paged memory pool for a user-defined extra create parameter (ECP) context structure and generates a pointer to that structure.

## -parameters

### -param Filter [in]

Opaque filter pointer for the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.

### -param EcpType [in]

Pointer to a user-defined GUID indicating the type of the ECP context structure.  See [Using GUIDs in Drivers](https://docs.microsoft.com/windows-hardware/drivers/kernel/using-guids-in-drivers) for more information.

### -param SizeOfContext [in]

The size, in bytes, of the user-defined context structure.

### -param Flags [in]

Defines pool allocation options.  The following describes how pool will be allocated when one or more of the listed flag values are combined with the *Flags* parameter by using a bitwise OR operation:  

- FSRTL_ALLOCATE_ECP_FLAG_NONPAGED_POOL - Non-paged pool will be allocated.  If this flag value is not used, paged pool will be allocated.

- FSRTL_ALLOCATE_ECPLIST_FLAG_CHARGE_QUOTA - All pool allocated by this routine will be charged against the current process' memory quota.

If more than one flag is used, all of the effects associated with the utilized flag values will occur.

### -param CleanupCallback [in, optional]

Optional pointer to a minifilter-defined cleanup callback routine of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff551124">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a>.  The cleanup callback routine is called when the ECP structure (created by the **FltAllocateExtraCreateParameter** routine) is deleted.  Set this parameter to **NULL** if a cleanup callback routine is not applicable.

### -param PoolTag [in]

Specifies the pool tag for the allocated memory. For more information, see the *Tag* parameter of [ExAllocatePoolWithTag](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exallocatepoolwithtag).

### -param EcpContext [out]

Receives a pointer to the allocated ECP context structure.  If the routine failed to allocate sufficient pool, *\*EcpContext* will be **NULL** and the routine will return status code STATUS_INSUFFICIENT_RESOURCES.

## -returns

**FltAllocateExtraCreateParameter** can return one of the following values:

|Return code|Description|
|----|----|
|STATUS_INSUFFICIENT_RESOURCES|**FltAllocateExtraCreateParameter** was unable to allocate sufficient memory for an ECP structure.  In this case, *EcpContext* will be **NULL**.|
|STATUS_SUCCESS|The ECP structure was successfully allocated.  In this case, a pointer to the allocated structure is returned in the *EcpContext* parameter.|

## -remarks

By default, the **FltAllocateExtraCreateParameter** routine allocates paged memory pool for a user-defined ECP context structure.  If the FSRTL_ALLOCATE_ECP_FLAG_NONPAGED_POOL bitmask is used as described above, a non-paged memory pool is allocated.  Once this pool has been allocated and the ECP context structure has been initialized, the [FltInsertExtraCreateParameter](https://msdn.microsoft.com/library/windows/hardware/ff543305) routine is used to insert the ECP context structure (ECP list element) into an ECP list structure (ECP list).

Memory pool that is allocated by the **FltAllocateExtraCreateParameter** routine is not automatically freed by the operating system.  This memory pool must eventually be released by using one of the following methods:

- Call the [FltRemoveExtraCreateParameter](nf-fltkernel-fltremoveextracreateparameter.md) routine to remove the ECP context structure from the ECP list and then call the [FltFreeExtraCreateParameter](nf-fltkernel-fltfreeextracreateparameter.md) routine to free the ECP context structure itself.  The ECP list remains in existence.

- Call the [FltFreeExtraCreateParameterList](nf-fltkernel-fltfreeextracreateparameterlist.md) routine - this frees the ECP list including any list elements (ECP context structures).  The ECP list is destroyed.

    However, if a file system or file system filter driver attaches an ECP to an existing or newly-created ECP_LIST while processing an IRP_MJ_CREATE request, this ECP is automatically cleaned up when the IRP completes. As a result, a filter driver does not have to clean up ECPs that are added dynamically. This allows a filter driver's ECP to be properly propagated across the reparse points--a process that can require multiple IRP_MJ_CREATE requests to be generated.

## -see-also

[ECP_LIST](https://msdn.microsoft.com/library/windows/hardware/ff540148)

[FltAllocateExtraCreateParameterFromLookasideList](nf-fltkernel-fltallocateextracreateparameterfromlookasidelist.md)

[FltAllocateExtraCreateParameterList](nf-fltkernel-fltallocateextracreateparameterlist.md)

[FltCreateFileEx2](nf-fltkernel-fltcreatefileex2.md)

[FltFreeExtraCreateParameter](nf-fltkernel-fltfreeextracreateparameter.md)

[FltFreeExtraCreateParameterList](nf-fltkernel-fltfreeextracreateparameterlist.md)

[FltGetEcpListFromCallbackData](nf-fltkernel-fltgetecplistfromcallbackdata.md)

[FltInsertExtraCreateParameter](nf-fltkernel-fltinsertextracreateparameter.md)

[FltRemoveExtraCreateParameter](nf-fltkernel-fltremoveextracreateparameter.md)

[FltSetEcpListIntoCallbackData](nf-fltkernel-fltremoveextracreateparameter.md)

[IoCreateFileEx](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-iocreatefileex)

[PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK](https://msdn.microsoft.com/library/windows/hardware/ff551124)
