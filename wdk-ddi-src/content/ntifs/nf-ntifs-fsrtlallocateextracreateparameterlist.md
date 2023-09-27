---
UID: NF:ntifs.FsRtlAllocateExtraCreateParameterList
title: FsRtlAllocateExtraCreateParameterList function (ntifs.h)
description: Learn more about the FsRtlAllocateExtraCreateParameterList function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["FsRtlAllocateExtraCreateParameterList function"]
ms.keywords: FsRtlAllocateExtraCreateParameterList, FsRtlAllocateExtraCreateParameterList routine [Installable File System Drivers], fsrtlref_2d552d23-4312-4203-91fb-c6cf6fb39681.xml, ifsk.fsrtlallocateextracreateparameterlist, ntifs/FsRtlAllocateExtraCreateParameterList
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows Vista
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
 - FsRtlAllocateExtraCreateParameterList
 - ntifs/FsRtlAllocateExtraCreateParameterList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlAllocateExtraCreateParameterList
---

# FsRtlAllocateExtraCreateParameterList function

## -description

The **FsRtlAllocateExtraCreateParameterList** routine allocates paged pool memory for an [**ECP_LIST**](/previous-versions/windows/hardware/drivers/ff540148(v=vs.85)) structure and generates a pointer to that structure.

## -parameters

### -param Flags [in]

Defines pool allocation options.  If the FSRTL_ALLOCATE_ECPLIST_FLAG_CHARGE_QUOTA flag is combined with the **Flags** parameter by using a bitwise OR operation, any pool allocated by **FsRtlAllocateExtraCreateParameterList**  will be charged against the current process' memory quota.

### -param EcpList [out]

Receives a pointer to an initialized ECP list structure.  If **FsRtlAllocateExtraCreateParameterList**  failed to allocate sufficient pool, ***EcpList** will be NULL and **FsRtlAllocateExtraCreateParameterList**  will return status code STATUS_INSUFFICIENT_RESOURCES.

## -returns

**FsRtlAllocateExtraCreateParameterList** can return one of the following values:

| Return code | Description |
| ----------- | ----------- |
| STATUS_INSUFFICIENT_RESOURCES | **FsRtlAllocateExtraCreateParameterList** was unable to allocate sufficient memory for an ECP list structure.  In this case, ***EcpList** will be NULL. |
| STATUS_SUCCESS  | The memory for the [**ECP_LIST**](/previous-versions/windows/hardware/drivers/ff540148(v=vs.85)) structure was successfully allocated and initialized.  In this case, a pointer to the initialized list structure is returned in the **EcpList** parameter. |

## -remarks

Whether the operating system automatically frees memory that **FsRtlAllocateExtraCreateParameterList** allocates depends on when **FsRtlAllocateExtraCreateParameterList** is called, as shown in the following situations:

* A caller can invoke **FsRtlAllocateExtraCreateParameterList** to allocate the ECP_LIST and add one or more ECP context structures before the caller invokes the [**IoCreateFileEx**](../ntddk/nf-ntddk-iocreatefileex.md) routine. In this situation, the operating system does not free any of the ECP context structures. Therefore, the caller can make multiple calls to **IoCreateFileEx** with the same ECP set. When the caller is done with the ECP_LIST, the caller must call the [**FltFreeExtraCreateParameter**](../fltkernel/nf-fltkernel-fltfreeextracreateparameter.md) routine to free the ECP_LIST.

* While a file system or file system filter driver processes an [**IRP_MJ_CREATE**](/windows-hardware/drivers/ifs/irp-mj-create) request, the file system or file system filter driver can call [**FltInsertExtraCreateParameter**](../fltkernel/nf-fltkernel-fltinsertextracreateparameter.md) to attach an ECP to an existing ECP_LIST. If the ECP_LIST does not exist, the caller must call **FsRtlAllocateExtraCreateParameterList** to create the ECP_LIST. In this situation, the ECP_LIST and the ECP context structure are automatically cleaned up by the I/O manager when the create operation completes. This allows a file system's or filter driver's ECP to be properly propagated across the processing of reparse points. This process might require multiple IRP_MJ_CREATE requests to be generated.

If the FSRTL_ALLOCATE_ECPLIST_FLAG_CHARGE_QUOTA flag is used with the **Flags** parameter, a pageable pool is allocated. Otherwise, a pageable pool is allocated by using an internal lookaside list.

## -see-also

[**ECP_LIST**](/previous-versions/windows/hardware/drivers/ff540148(v=vs.85))

[**FltAllocateExtraCreateParameter**](../fltkernel/nf-fltkernel-fltallocateextracreateparameter.md)

[**FltAllocateExtraCreateParameterFromLookasideList**](../fltkernel/nf-fltkernel-fltallocateextracreateparameterfromlookasidelist.md)

[**FltCreateFileEx2**](../fltkernel/nf-fltkernel-fltcreatefileex2.md)

[**FltFreeExtraCreateParameter**](../fltkernel/nf-fltkernel-fltfreeextracreateparameter.md)

[**FltFreeExtraCreateParameterList**](../fltkernel/nf-fltkernel-fltfreeextracreateparameterlist.md)

[**FltGetEcpListFromCallbackData**](../fltkernel/nf-fltkernel-fltgetecplistfromcallbackdata.md)

[**FltInsertExtraCreateParameter**](../fltkernel/nf-fltkernel-fltinsertextracreateparameter.md)

[**FltRemoveExtraCreateParameter**](../fltkernel/nf-fltkernel-fltremoveextracreateparameter.md)

[**FltSetEcpListIntoCallbackData**](../fltkernel/nf-fltkernel-fltsetecplistintocallbackdata.md)

[**IoCreateFileEx**](../ntddk/nf-ntddk-iocreatefileex.md)
