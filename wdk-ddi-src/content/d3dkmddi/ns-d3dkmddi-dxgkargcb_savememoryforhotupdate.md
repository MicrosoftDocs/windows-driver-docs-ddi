---
UID: NS:d3dkmddi._DXGKARGCB_SAVEMEMORYFORHOTUPDATE
title: DXGKARGCB_SAVEMEMORYFORHOTUPDATE
author: windows-driver-content
description: Arguments used in the DXGKCB_SAVEMEMORYFORHOTUPDATE callback function, to save memory for driver hot update.
tech.root: display
ms.assetid: 9def351b-6e64-4499-96ce-421b9be67c00
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["DXGKARGCB_SAVEMEMORYFORHOTUPDATE structure"]
f1_keywords:
 - "d3dkmddi/DXGKARGCB_SAVEMEMORYFORHOTUPDATE"
ms.keywords: DXGKARGCB_SAVEMEMORYFORHOTUPDATE, DXGKARGCB_SAVEMEMORYFORHOTUPDATE, 
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
req.typenames: DXGKARGCB_SAVEMEMORYFORHOTUPDATE
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - d3dkmddi.h
api_name: 
 - DXGKARGCB_SAVEMEMORYFORHOTUPDATE
product:
- Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: DXGKDDI_INTERFACE_VERSION_WDDM2_6, 19H1
---

# DXGKARGCB_SAVEMEMORYFORHOTUPDATE structure

## -description

Arguments used in the [DXGKCB_SAVEMEMORYFORHOTUPDATE](nc-d3dkmddi-dxgkcb_savememoryforhotupdate.md) callback function, to save memory for driver hot update.

## -struct-fields

### -field NumDataMemoryRanges

[in] The number of physical memory ranges in the *pDataMemoryRanges* array.

### -field pDataMemoryRanges

[in, optional] Pointer to the array of physical memory ranges.

### -field pDataMdl

[in, optional] Pointer to an MDL (memory descriptor list), which describes physical memory pages.

When passing *pDataMdl* the driver should do the following:

* Compute how much memory to allocated
* [MmAllocatePagesForMdlEx](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatepagesformdlex)
* [MmMapLockedPagesSpecifyCache](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmmaplockedpagesspecifycache)
* Copy description of the data to the buffer
* Copy data into pages from internal data structures
* [MmUnmapLockedPages](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmunmaplockedpages)
* Give MDL to Dxgkrnl

### -field DataSize

[in] The number of bytes in the buffer that *pData* points to.

### -field pData

[in, optional] A pointer to the virtual memory to save.

### -field MetaDataSize

[in] The number of bytes in the buffer that *pMetaData* points to.

### -field pMetaData

[in, optional] The virtual memory pointer to metadata that is associated with the saved memory block.

## -remarks

The driver must not save the same physical page twice.

## -see-also
