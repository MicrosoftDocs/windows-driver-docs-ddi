---
UID: NS:d3dkmddi._DXGKARG_RESTOREMEMORYFORHOTUPDATE
title: DXGKARG_RESTOREMEMORYFORHOTUPDATE
author: windows-driver-content
description: Arguments used to restore memory for driver hot update.
tech.root: display
ms.assetid: 758482bb-b832-4749-9a3b-17670fc65156
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["DXGKARG_RESTOREMEMORYFORHOTUPDATE structure"]
f1_keywords:
 - "d3dkmddi/DXGKARG_RESTOREMEMORYFORHOTUPDATE"
 - "DXGKARG_RESTOREMEMORYFORHOTUPDATE"
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
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - d3dkmddi.h
api_name: 
 - DXGKARG_RESTOREMEMORYFORHOTUPDATE
product:
- Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: DXGKDDI_INTERFACE_VERSION_WDDM2_6, 19H1
---

# DXGKARG_RESTOREMEMORYFORHOTUPDATE structure

## -description

Arguments used to restore memory for driver hot update.

## -struct-fields

### -field Flags

[in] A [DXGK_RESTOREMEMORYFORHOTUPDATEFLAGS](ns-d3dkmddi-dxgk_restorememoryforhotupdateflags.md) structure. When the flag is set, all other input data is set to NULL. The driver can delete all memory, allocated during restore operation.

### -field pDataMdl

[in] The MDL (memory descriptor list), which describes the memory pages to restore.

If the driver returns STATUS_SUCCESS from this function, the driver assumes the ownership of the MDL. The driver can keep the pointer to the MDL until it is no longer used. After that the driver must free the MDL pages and the MDL itself by calling [MmFreePagesFromMdl(pDataMdl)](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmfreepagesfrommdl) and [ExFreePool(pDataMdl)](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exfreepool).

The driver can use [MmMapLockedPagesSpecifyCache](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmmaplockedpagesspecifycache) or [MmGetSystemAddressForMdlSafe](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmgetsystemaddressformdl) to get a CPU pointer to the buffer.

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
