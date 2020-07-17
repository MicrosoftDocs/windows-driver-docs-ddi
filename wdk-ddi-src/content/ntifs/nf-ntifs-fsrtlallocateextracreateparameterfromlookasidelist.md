---
UID: NF:ntifs.FsRtlAllocateExtraCreateParameterFromLookasideList
title: FsRtlAllocateExtraCreateParameterFromLookasideList function (ntifs.h)
description: The FsRtlAllocateExtraCreateParameterFromLookasideList routine allocates memory pool from a given lookaside list for an extra create parameter (ECP) context structure, and generates a pointer to that structure.
old-location: ifsk\fsrtlallocateextracreateparameterfromlookasidelist.htm
tech.root: ifsk
ms.assetid: 6dd1aa9d-58e6-484b-b372-4c1d9f6d04f3
ms.date: 04/16/2018
keywords: ["FsRtlAllocateExtraCreateParameterFromLookasideList function"]
ms.keywords: FsRtlAllocateExtraCreateParameterFromLookasideList, FsRtlAllocateExtraCreateParameterFromLookasideList routine [Installable File System Drivers], fsrtlref_c85ee3ff-e71f-4c6e-bc37-4187cad9855f.xml, ifsk.fsrtlallocateextracreateparameterfromlookasidelist, ntifs/FsRtlAllocateExtraCreateParameterFromLookasideList
f1_keywords:
 - "ntifs/FsRtlAllocateExtraCreateParameterFromLookasideList"
 - "FsRtlAllocateExtraCreateParameterFromLookasideList"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: FsRtlAllocateExtraCreateParameterFromLookasideList is available starting with Windows Vista.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlAllocateExtraCreateParameterFromLookasideList
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlAllocateExtraCreateParameterFromLookasideList function

## -description

The **FsRtlAllocateExtraCreateParameterFromLookasideList** routine allocates memory pool from a given lookaside list for an extra create parameter (ECP) context structure, and generates a pointer to that structure.

## -parameters

### -param EcpType [in]

Pointer to a GUID that indicates the type of ECP for whicha context structure should be allocated. For more information about ECPs, see [Using Extra Create Parameters with an IRP_MJ_CREATE Operation](https://docs.microsoft.com/windows-hardware/drivers/ifs/using-extra-create-parameters-with-an-irp-mj-create-operation).

### -param SizeOfContext [in]

The size, in bytes, of the ECP context structure.

### -param Flags [in]

Defines pool allocation options. If the value of the *SizeOfContext* parameter is larger than the size, in bytes, of the lookaside list that the *LookasideList* parameter points to, **FsRtlAllocateExtraCreateParameterFromLookasideList** allocates the ECP context structure from system pool instead of the lookaside list. In this case, if the *Flags* parameter contains the FSRTL_ALLOCATE_ECP_FLAG_CHARGE_QUOTA bit flag value, system pool allocated by **FsRtlAllocateExtraCreateParameterFromLookasideList** is charged against the current process' memory quota. For more information about bit flag values, see the *Flags* parameter of [FsRtlAllocateExtraCreateParameter](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlallocateextracreateparameter). In the more typical case, when **FsRtlAllocateExtraCreateParameterFromLookasideList** allocates memory for the ECP context structure from the lookaside list, **FsRtlAllocateExtraCreateParameterFromLookasideList** ignores the FSRTL_ALLOCATE_ECP_FLAG_CHARGE_QUOTA bit flag.

### -param CleanupCallback [in, optional]

Optional pointer to a minifilter-defined cleanup callback routine of type [PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nc-ntifs-pfsrtl_extra_create_parameter_cleanup_callback). The cleanup callback routine is called when the ECP context structure is deleted. Set this parameter to **NULL** if a cleanup callback routine is not applicable.

### -param LookasideList [in, out]

Pointer to an initialized lookaside list from which **FsRtlAllocateExtraCreateParameterFromLookasideList** attempts to allocate pool (for the ECP context structure). To initialize the lookaside list, use the [FsRtlInitExtraCreateParameterLookasideList](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlinitextracreateparameterlookasidelist) routine.

### -param EcpContext [out]

Pointer to a location that receives a pointer to the allocated ECP context structure. If **FsRtlAllocateExtraCreateParameterFromLookasideList** failed to allocate sufficient pool for the ECP context structure, **FsRtlAllocateExtraCreateParameterFromLookasideList** sets *EcpContext* to **NULL** and returns status code STATUS_INSUFFICIENT_RESOURCES.

## -returns

The **FsRtlAllocateExtraCreateParameterFromLookasideList** routine can return one of the following values:

|Return code|Description|
|---|---|
|STATUS_INSUFFICIENT_RESOURCES|The **FsRtlAllocateExtraCreateParameterFromLookasideList** routine was unable to allocate sufficient memory for an ECP context structure. In this case, the *EcpContext* parameter is **NULL**.|
|STATUS_SUCCESS|The ECP context structure was successfully allocated. In this case, **FsRtlAllocateExtraCreateParameterFromLookasideList** returns a pointer to the allocated structure in the *EcpContext* parameter.|

## -remarks

Use the [FsRtlInitExtraCreateParameterLookasideList](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlinitextracreateparameterlookasidelist) routine to initialize a paged or nonpaged pool lookaside list. Use the **FsRtlAllocateExtraCreateParameterFromLookasideList** routine to allocate an ECP context structure from the lookaside list, and the [FsRtlFreeExtraCreateParameter](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlfreeextracreateparameter) routine to deallocate the ECP context structure.

Use the [FsRtlDeleteExtraCreateParameterLookasideList](https://msdn.microsoft.com/library/windows/hardware/ff545849) routine to free a lookaside list.

Drivers must free all ECP context structures and lookaside lists they create before unloading. However, if a file system or file system filter driver attaches an ECP to an existing or newly-created **ECP_LIST** while processing an **IRP_MJ_CREATE** request, this ECP is automatically cleaned up when the IRP completes. As a result, a filter driver does not have to clean up ECPs that are added dynamically. This allows a filter driver's ECP to be properly propagated across the re-parse points, a process that can require multiple **IRP_MJ_CREATE** requests to be generated.

For more information about using lookaside lists with drivers, see [Using Lookaside Lists](https://docs.microsoft.com/windows-hardware/drivers/kernel/using-lookaside-lists).

## -see-also

[FsRtlDeleteExtraCreateParameterLookasideList](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtldeleteextracreateparameterlookasidelist)

[FsRtlFreeExtraCreateParameter](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlfreeextracreateparameter)

[FsRtlInitExtraCreateParameterLookasideList](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlinitextracreateparameterlookasidelist)

[PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nc-ntifs-pfsrtl_extra_create_parameter_cleanup_callback)
