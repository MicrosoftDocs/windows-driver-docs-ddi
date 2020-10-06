---
UID: NF:fltkernel.FltAllocateExtraCreateParameterFromLookasideList
title: FltAllocateExtraCreateParameterFromLookasideList function (fltkernel.h)
description: The FltAllocateExtraCreateParameterFromLookasideList routine allocates memory pool from a given lookaside list for an extra create parameter (ECP) context structure and generates a pointer to that structure.
old-location: ifsk\fltallocateextracreateparameterfromlookasidelist.htm
tech.root: ifsk
ms.assetid: 33ab7ff3-d9b0-43ad-9971-62735f3240df
ms.date: 04/16/2018
keywords: ["FltAllocateExtraCreateParameterFromLookasideList function"]
ms.keywords: FltAllocateExtraCreateParameterFromLookasideList, FltAllocateExtraCreateParameterFromLookasideList routine [Installable File System Drivers], FltApiRef_a_to_d_27580c4f-61c2-46b1-be1c-8895c918a05e.xml, fltkernel/FltAllocateExtraCreateParameterFromLookasideList, ifsk.fltallocateextracreateparameterfromlookasidelist
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltAllocateExtraCreateParameterFromLookasideList
 - fltkernel/FltAllocateExtraCreateParameterFromLookasideList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - fltmgr.lib
 - fltmgr.sys
api_name:
 - FltAllocateExtraCreateParameterFromLookasideList
---

# FltAllocateExtraCreateParameterFromLookasideList function


## -description

The **FltAllocateExtraCreateParameterFromLookasideList** routine allocates memory pool from a given lookaside list for an extra create parameter (ECP) context structure and generates a pointer to that structure.

## -parameters

### -param Filter 

[in]
Opaque filter pointer to the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.

### -param EcpType 

[in]
Pointer to a GUID that indicates the type of the ECP context structure.  See [Using GUIDs in Drivers](/windows-hardware/drivers/kernel/using-guids-in-drivers) for more information.

### -param SizeOfContext 

[in]
The size, in bytes, of the ECP context structure.

### -param Flags 

[in]
Defines pool allocation options.  If the value of the *SizeOfContext* parameter is larger than the size, in bytes, of the given lookaside list, the ECP context structure will be allocated from system pool instead of the lookaside list.  In this case, if the *Flags* parameter contains the FSRTL_ALLOCATE_ECP_FLAG_CHARGE_QUOTA bit flag value, system pool allocated by the routine will be charged against the current process' memory quota. See the *Flags* parameter of [FltAllocateExtraCreateParameter](nf-fltkernel-fltallocateextracreateparameter.md) for more information.  In the more typical case when memory for the ECP context structure is allocated from the lookaside list, the FSRTL_ALLOCATE_ECP_FLAG_CHARGE_QUOTA bit flag is not used by the routine.

### -param CleanupCallback 

[in, optional]
Optional pointer to a minifilter-defined cleanup callback routine of type [PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK](/previous-versions/ff551124(v=vs.85)).  The cleanup callback routine is called when the ECP context structure is deleted.  Set this parameter to **NULL** if a cleanup callback routine is not applicable.

### -param LookasideList 

[in, out]
Pointer to an initialized lookaside list in which to attempt to allocate pool from (for the ECP context structure).  To initialize the lookaside list, use the [FltInitExtraCreateParameterLookasideList](./nf-fltkernel-fltinitextracreateparameterlookasidelist.md) routine.

### -param EcpContext 

[out]
Receives a pointer to the allocated ECP context structure.  If the routine failed to allocate sufficient pool for the ECP context structure, *EcpContext* will be **NULL** and the routine will return status code STATUS_INSUFFICIENT_RESOURCES.

## -returns

The **FltAllocateExtraCreateParameterFromLookasideList** routine can return one of the following values:

|Return code|Description|
|----|----|
|**STATUS_INSUFFICIENT_RESOURCES**|The **FltAllocateExtraCreateParameterFromLookasideList** routine was unable to allocate sufficient memory for an ECP context structure.  In this case, *EcpContext* will be **NULL**.|
|**STATUS_SUCCESS**|The ECP context structure was successfully allocated.  In this case, a pointer to the allocated structure is returned by the *EcpContext* parameter.

## -remarks

This routine is available starting with Windows Vista. 

The **FltAllocateExtraCreateParameterFromLookasideList** routine allocates memory pool for an ECP context structure from the given initialized paged or non-paged lookaside list.  However, if the size of the ECP context structure (as defined by the *SizeOfContext*  parameter) is larger than the lookaside list, the routine analogously allocates memory from paged or non-paged system pool.

Use the [FltInitExtraCreateParameterLookasideList](nf-fltkernel-fltinitextracreateparameterlookasidelist.md) routine to initialize a paged or non-paged pool lookaside list. Use the **FltAllocateExtraCreateParameterFromLookasideList** routine to allocate an ECP context structure from the lookaside list, and the [FltFreeExtraCreateParameter](nf-fltkernel-fltfreeextracreateparameter.md) routine to deallocate the ECP context structure.

Use the [FltDeleteExtraCreateParameterLookasideList](nf-fltkernel-fltdeleteextracreateparameterlookasidelist.md) routine to free a lookaside list.

Drivers must free all ECP context structures and lookaside lists they create before unloading. However, if a file system or file system filter driver attaches an ECP to an existing or newly-created ECP_LIST while processing an IRP_MJ_CREATE request, this ECP is automatically cleaned up when the IRP completes. As a result, a filter driver does not have to clean up ECPs that are added dynamically. This allows a filter driver's ECP to be properly propagated across the reparse points--a process that can require multiple IRP_MJ_CREATE requests to be generated.

For more information about using lookaside lists with drivers, see [Using Lookaside Lists](/windows-hardware/drivers/kernel/using-lookaside-lists).

## -see-also

[ECP_LIST](/previous-versions/windows/hardware/drivers/ff540148(v=vs.85))

[FltAllocateExtraCreateParameter](nf-fltkernel-fltallocateextracreateparameter.md)

[FltAllocateExtraCreateParameterList](nf-fltkernel-fltallocateextracreateparameterlist.md)

[FltCreateFileEx2](nf-fltkernel-fltcreatefileex2.md)

[FltDeleteExtraCreateParameterLookasideList](nf-fltkernel-fltdeleteextracreateparameterlookasidelist.md)

[FltFreeExtraCreateParameter](nf-fltkernel-fltfreeextracreateparameter.md)

[FltFreeExtraCreateParameterList](nf-fltkernel-fltfreeextracreateparameterlist.md)

[FltGetEcpListFromCallbackData](nf-fltkernel-fltgetecplistfromcallbackdata.md)

[FltInitExtraCreateParameterLookasideList](nf-fltkernel-fltinitextracreateparameterlookasidelist.md)

[FltInsertExtraCreateParameter](nf-fltkernel-fltinsertextracreateparameter.md)

[FltRemoveExtraCreateParameter](nf-fltkernel-fltremoveextracreateparameter.md)

[FltSetEcpListIntoCallbackData](nf-fltkernel-fltsetecplistintocallbackdata.md)

[IoCreateFileEx](../ntddk/nf-ntddk-iocreatefileex.md)

[PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK](/previous-versions/ff551124(v=vs.85))