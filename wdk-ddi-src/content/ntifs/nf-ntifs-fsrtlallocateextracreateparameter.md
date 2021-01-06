---
UID: NF:ntifs.FsRtlAllocateExtraCreateParameter
title: FsRtlAllocateExtraCreateParameter function (ntifs.h)
description: The FsRtlAllocateExtraCreateParameter routine allocates memory for a user-defined extra create parameter (ECP) context structure and generates a pointer to that structure.
old-location: ifsk\fsrtlallocateextracreateparameter.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FsRtlAllocateExtraCreateParameter function"]
ms.keywords: FsRtlAllocateExtraCreateParameter, FsRtlAllocateExtraCreateParameter routine [Installable File System Drivers], fsrtlref_97f1c552-b822-4fda-9327-8d127f42080b.xml, ifsk.fsrtlallocateextracreateparameter, ntifs/FsRtlAllocateExtraCreateParameter
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlAllocateExtraCreateParameter
 - ntifs/FsRtlAllocateExtraCreateParameter
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlAllocateExtraCreateParameter
---

# FsRtlAllocateExtraCreateParameter function


## -description

The **FsRtlAllocateExtraCreateParameter** routine allocates memory for a user-defined extra create parameter (ECP) context structure and generates a pointer to that structure.

## -parameters

### -param EcpType 

[in]
A pointer to a user-defined GUID that indicates the type of the ECP context structure.  See [Using GUIDs in Drivers](/windows-hardware/drivers/kernel/using-guids-in-drivers) for more information.

### -param SizeOfContext 

[in]
The size, in bytes, of the user-defined context structure.

### -param Flags 

[in]
Defines pool allocation options.  The following describes how pool will be allocated when one or more of the listed flag values are combined with the *Flags* parameter by using a bitwise OR operation:  

- FSRTL_ALLOCATE_ECP_FLAG_NONPAGED_POOL - Non-paged pool will be allocated.  If this flag value is not used, paged pool will be allocated.

- FSRTL_ALLOCATE_ECPLIST_FLAG_CHARGE_QUOTA - All pool allocated by **FsRtlAllocateExtraCreateParameter** will be charged against the current process' memory quota.

If more than one flag is used, all of the effects associated with the utilized flag values will occur.

### -param CleanupCallback 

[in, optional]
Optional pointer to a filter-defined cleanup callback routine of type [PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK](/previous-versions/ff551124(v=vs.85)).  The cleanup callback routine is called when the ECP structure (created by the **FsRtlAllocateExtraCreateParameter** routine) is deleted.  Set this parameter to **NULL** if a cleanup callback routine is not applicable.

### -param PoolTag 

[in]
Specifies the pool tag for the allocated memory. For more information, see the *Tag* parameter of [ExAllocatePoolWithTag](../wdm/nf-wdm-exallocatepoolwithtag.md).

### -param EcpContext 

[out]
Receives a pointer to the allocated ECP context structure.  If the routine failed to allocate sufficient pool, the value pointed to by *EcpContext* will be **NULL** and **FsRtlAllocateExtraCreateParameter** will return status code STATUS_INSUFFICIENT_RESOURCES.

## -returns

**FltAllocateExtraCreateParameter** can return one of the following values:

|Return code|Description|
|----|----|
|**STATUS_INSUFFICIENT_RESOURCES**|**FsRtlAllocateExtraCreateParameter** was unable to allocate sufficient memory for an ECP structure.  In this case, *EcpContext* is **NULL**.|
|**STATUS_SUCCESS**|The ECP structure was successfully allocated.  In this case, a pointer to the allocated structure is returned in the *EcpContext* parameter.

## -remarks

By default, the **FsRtlAllocateExtraCreateParameter** routine allocates paged memory pool for a user-defined ECP context structure.  If the FSRTL_ALLOCATE_ECP_FLAG_NONPAGED_POOL bitmask is used as described in the *Flags* parameter, a non-paged memory pool is allocated.  After this pool has been allocated and the ECP context structure has been initialized, the [FltInsertExtraCreateParameter](../fltkernel/nf-fltkernel-fltinsertextracreateparameter.md) routine is used to insert the ECP context structure (ECP list element) into an ECP list structure ([ECP_LIST](/previous-versions/windows/hardware/drivers/ff540148(v=vs.85))).

If the caller allocates ECP_LIST and one or more ECPs are used in a call to [IoCreateFileEx](../ntddk/nf-ntddk-iocreatefileex.md), the previous description is correct. In this case, the system does not free any of the ECPs, so the caller can make multiple calls to **IoCreateFileEx** with the same ECP set. However, if a file system or file system filter driver attaches an ECP to an existing or newly-created ECP_LIST while processing an IRP_MJ_CREATE request, this ECP is automatically cleaned up when the IRP completes. As a result, a filter driver does not have to clean up ECPs that are added dynamically. This allows a filter driver's ECP to be properly propagated across the reparse points--a process that can require multiple IRP_MJ_CREATE requests to be generated.

## -see-also

[ECP_LIST](/previous-versions/windows/hardware/drivers/ff540148(v=vs.85))

[FltAllocateExtraCreateParameterFromLookasideList](../fltkernel/nf-fltkernel-fltallocateextracreateparameterfromlookasidelist.md)

[FltAllocateExtraCreateParameterList](../fltkernel/nf-fltkernel-fltallocateextracreateparameterlist.md)

[FltCreateFileEx2](../fltkernel/nf-fltkernel-fltcreatefileex2.md)

[FltFreeExtraCreateParameter](../fltkernel/nf-fltkernel-fltfreeextracreateparameter.md)

[FltFreeExtraCreateParameterList](../fltkernel/nf-fltkernel-fltfreeextracreateparameterlist.md)

[FltGetEcpListFromCallbackData](../fltkernel/nf-fltkernel-fltgetecplistfromcallbackdata.md)

[FltInsertExtraCreateParameter](../fltkernel/nf-fltkernel-fltinsertextracreateparameter.md)

[FltRemoveExtraCreateParameter](../fltkernel/nf-fltkernel-fltremoveextracreateparameter.md)

[FltSetEcpListIntoCallbackData](../fltkernel/nf-fltkernel-fltsetecplistintocallbackdata.md)

[IoCreateFileEx](../ntddk/nf-ntddk-iocreatefileex.md)

[PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK](/previous-versions/ff551124(v=vs.85))
