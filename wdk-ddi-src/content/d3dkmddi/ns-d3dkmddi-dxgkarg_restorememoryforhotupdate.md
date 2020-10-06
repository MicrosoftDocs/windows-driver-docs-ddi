---
UID: NS:d3dkmddi._DXGKARG_RESTOREMEMORYFORHOTUPDATE
title: DXGKARG_RESTOREMEMORYFORHOTUPDATE
description: Arguments used to restore memory for driver hot update.
tech.root: display
ms.assetid: 758482bb-b832-4749-9a3b-17670fc65156
ms.date: 04/04/2019
keywords: ["DXGKARG_RESTOREMEMORYFORHOTUPDATE structure"]
ms.keywords: DXGKARG_RESTOREMEMORYFORHOTUPDATE, DXGKARG_RESTOREMEMORYFORHOTUPDATE,
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGKARG_RESTOREMEMORYFORHOTUPDATE
targetos: Windows
ms.custom: DXGKDDI_INTERFACE_VERSION_WDDM2_6, 19H1
f1_keywords:
 - _DXGKARG_RESTOREMEMORYFORHOTUPDATE
 - d3dkmddi/_DXGKARG_RESTOREMEMORYFORHOTUPDATE
 - DXGKARG_RESTOREMEMORYFORHOTUPDATE
 - d3dkmddi/DXGKARG_RESTOREMEMORYFORHOTUPDATE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGKARG_RESTOREMEMORYFORHOTUPDATE
dev_langs:
 - c++
---

# DXGKARG_RESTOREMEMORYFORHOTUPDATE structure


## -description

Arguments used to restore memory for driver hot update.

## -struct-fields

### -field Flags

[in] A [DXGK_RESTOREMEMORYFORHOTUPDATEFLAGS](ns-d3dkmddi-dxgk_restorememoryforhotupdateflags.md) structure. When the flag is set, all other input data is set to NULL. The driver can delete all memory, allocated during restore operation.

### -field pDataMdl

[in] The MDL (memory descriptor list), which describes the memory pages to restore.

If the driver returns STATUS_SUCCESS from this function, the driver assumes the ownership of the MDL. The driver can keep the pointer to the MDL until it is no longer used. After that the driver must free the MDL pages and the MDL itself by calling [MmFreePagesFromMdl(pDataMdl)](../wdm/nf-wdm-mmfreepagesfrommdl.md) and [ExFreePool(pDataMdl)](../wdm/nf-wdm-exfreepool.md).

The driver can use [MmMapLockedPagesSpecifyCache](../wdm/nf-wdm-mmmaplockedpagesspecifycache.md) or [MmGetSystemAddressForMdlSafe](../wdm/nf-wdm-mmgetsystemaddressformdl.md) to get a CPU pointer to the buffer.

Here is an example of how you would get a CPU pointer to the buffer:

```cpp
pBuffer = MmMapLockedPagesSpecifyCache(
    pMdl,
    KernelMode,
    MmCached,
    NULL,
    FALSE,
    NormalPagePriority | MdlMappingNoExecute);

pBuffer = MmGetSystemAddressForMdlSafe(pMdl, NormalPagePriority | MdlMappingNoExecute);
```

### -field MetaDataSize

[in] The number of bytes in the buffer that *pMetaData* points to.

### -field pMetaData

 
[in] A virtual memory pointer to the metadata that is associated with the memory block.

## -remarks

## -see-also