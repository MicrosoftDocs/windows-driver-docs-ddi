---
UID: NF:fltkernel.FltAllocateExtraCreateParameterList
title: FltAllocateExtraCreateParameterList function (fltkernel.h)
description: The FltAllocateExtraCreateParameterList routine allocates paged pool memory for an extra create parameter (ECP) list structure and generates a pointer to that structure.
old-location: ifsk\fltallocateextracreateparameterlist.htm
tech.root: ifsk
ms.assetid: 0130e35f-a6a8-4fa9-9922-1d1d0f43cb2a
ms.date: 04/16/2018
keywords: ["FltAllocateExtraCreateParameterList function"]
ms.keywords: FltAllocateExtraCreateParameterList, FltAllocateExtraCreateParameterList routine [Installable File System Drivers], FltApiRef_a_to_d_9caf46c0-e0bb-4a0a-b9dd-f4005664b9ca.xml, fltkernel/FltAllocateExtraCreateParameterList, ifsk.fltallocateextracreateparameterlist
f1_keywords:
 - "fltkernel/FltAllocateExtraCreateParameterList"
 - "FltAllocateExtraCreateParameterList"
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available starting with Windows Vista.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- FltMgr.lib
- FltMgr.dll
api_name:
- FltAllocateExtraCreateParameterList
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltAllocateExtraCreateParameterList function

## -description

The **FltAllocateExtraCreateParameterList** routine allocates paged pool memory for an extra create parameter (ECP) list structure and generates a pointer to that structure.

## -parameters

### -param Filter [in]

Opaque filter pointer for the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.

### -param Flags [in]

Defines pool allocation options.  If the FSRTL_ALLOCATE_ECPLIST_FLAG_CHARGE_QUOTA flag is combined with the *Flags* parameter by using a bitwise OR operation, any pool allocated by the routine will be charged against the current process' memory quota.

### -param EcpList [out]

Receives a pointer to an initialized ECP list structure.  If the routine failed to allocate sufficient pool, *\*EcpList* will be **NULL** and the routine will return status code STATUS_INSUFFICIENT_RESOURCES.

## -returns

**FltAllocateExtraCreateParameterList** can return one of the following values:

|Return code|Description|
|----|----|
|**STATUS_INSUFFICIENT_RESOURCES**|**FltAllocateExtraCreateParameterList** was unable to allocate sufficient memory for an ECP list structure.  In this case, *\*EcpList* will be **NULL**.|
|**STATUS_SUCCESS**|The ECP list structure was successfully allocated and initialized.  In this case, a pointer to the initialized list structure is returned in the *\*EcpList* parameter.|

## -remarks

Whether the operating system automatically frees memory that **FltAllocateExtraCreateParameterList** allocates depends on when **FltAllocateExtraCreateParameterList** is called, as shown in the following situations:

- A caller can invoke **FltAllocateExtraCreateParameterList** to allocate the ECP_LIST and add one or more ECP context structures before the caller invokes the [FltCreateFileEx2](nf-fltkernel-fltcreatefileex2.md) routine. In this situation, the operating system does not free any of the ECP context structures. Therefore, the caller can make multiple calls to **FltCreateFileEx2** with the same ECP set. When the caller is done with the ECP_LIST, the caller must call the [FltFreeExtraCreateParameterList](nf-fltkernel-fltfreeextracreateparameterlist.md) routine to free the ECP_LIST.

- While a file system filter driver processes an [IRP_MJ_CREATE](https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-create) request, the file system filter driver can call [FltInsertExtraCreateParameter](nf-fltkernel-fltinsertextracreateparameter.md) to attach an ECP to an existing ECP_LIST. If the ECP_LIST does not exist, the caller must call **FltAllocateExtraCreateParameterList** to create the ECP_LIST. In this situation, the ECP_LIST and the ECP context structure are automatically cleaned up by the I/O manager when the create operation completes. This allows a filter driver's ECP to be properly propagated across the processing of reparse points. This process might require multiple IRP_MJ_CREATE requests to be generated.

If the FSRTL_ALLOCATE_ECPLIST_FLAG_CHARGE_QUOTA flag is used with the *Flags* parameter, as described above, a normal pageable pool is allocated. Otherwise, a pageable pool is allocated by using an internal lookaside list.

### ECP_LIST structure

ECP_LIST is an opaque structure that is declared by the operating system. ECP_LIST contains a list of extra create parameter (ECP) entries.

The **FltAllocateExtraCreateParameterList** routine must be used to allocate memory for the **ECP_LIST** structure. The memory allocated by **FltAllocateExtraCreateParameterList** is not automatically freed by the operating system; it must be explicitly deallocated by calling the **FltFreeExtraCreateParameterList** routine. Note that any remaining ECP list elements will be automatically freed when **FltFreeExtraCreateParameterList** is called.

The PECP_LIST data type is used to declare a pointer to a variable of type ECP_LIST.

#### Syntax

```c++
struct ECP_LIST {
  ;      // Reserved.
};
```

The ECP_LIST structure is declared in Ntifs.h (include Ntifs.h).

## -see-also

[FltAllocateExtraCreateParameter](nf-fltkernel-fltallocateextracreateparameter.md)

[FltAllocateExtraCreateParameterFromLookasideList](nf-fltkernel-fltallocateextracreateparameterfromlookasidelist.md)

[FltCreateFileEx2](nf-fltkernel-fltcreatefileex2.md)

[FltFreeExtraCreateParameter](nf-fltkernel-fltfreeextracreateparameter.md)

[FltFreeExtraCreateParameterList](nf-fltkernel-fltfreeextracreateparameterlist.md)

[FltGetEcpListFromCallbackData](nf-fltkernel-fltgetecplistfromcallbackdata.md)

[FltInsertExtraCreateParameter](nf-fltkernel-fltinsertextracreateparameter.md)

[FltRemoveExtraCreateParameter](nf-fltkernel-fltremoveextracreateparameter.md)

[FltSetEcpListIntoCallbackData](nf-fltkernel-fltsetecplistintocallbackdata.md)

[IoCreateFileEx](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex)
