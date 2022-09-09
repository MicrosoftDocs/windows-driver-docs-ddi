---
UID: NS:d3dkmddi._DXGK_ALLOCATIONINFOFLAGS2
tech.root: display
title: DXGK_ALLOCATIONINFOFLAGS2
ms.date: 09/08/2022
targetos: Windows
description: Learn more about the DXGK_ALLOCATIONINFOFLAGS2 structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGK_ALLOCATIONINFOFLAGS2
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_ALLOCATIONINFOFLAGS2
 - DXGK_ALLOCATIONINFOFLAGS2
f1_keywords:
 - _DXGK_ALLOCATIONINFOFLAGS2
 - d3dkmddi/_DXGK_ALLOCATIONINFOFLAGS2
 - DXGK_ALLOCATIONINFOFLAGS2
 - d3dkmddi/DXGK_ALLOCATIONINFOFLAGS2
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_ALLOCATIONINFOFLAGS2
---

## -description

The **DXGK_ALLOCATIONINFOFLAGS2** structure contains additional properties for an allocation.

## -struct-fields

### -field ShareBackingStoreWithKmd

When set, the kernel-mode driver is notifying *Dxgkrnl* that it needs to know the address of the allocation backing store. The allocation must be created shared and must reside only in the aperture memory segment.

### -field Reserved

Reserved; do not use.

### -field Value

An alternative way to access the bits.

## -remarks

## -see-also

[**DXGK_ALLOCATIONINFO**](ns-d3dkmddi-_dxgk_allocationinfo.md)

[**DXGKDDI_CREATEALLOCATION**](nc-d3dkmddi-dxgkddi_createallocation.md)
