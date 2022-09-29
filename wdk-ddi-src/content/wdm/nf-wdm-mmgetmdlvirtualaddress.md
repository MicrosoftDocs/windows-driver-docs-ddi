---
UID: NF:wdm.MmGetMdlVirtualAddress
tech.root: 
title: MmGetMdlVirtualAddress
ms.date: 07/16/2021
targetos: Windows
description: "Learn more about: MmGetMdlVirtualAddress"
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: Any level (see Remarks)
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 2000
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - MmGetMdlVirtualAddress
f1_keywords:
 - MmGetMdlVirtualAddress
 - wdm/MmGetMdlVirtualAddress
dev_langs:
 - c++
---

## -description

The **MmGetMdlVirtualAddress** macro returns the base virtual address of a buffer described by an MDL.

## -syntax

```cpp
PVOID
MmGetMdlVirtualAddress (
    _In_ PMDL Mdl
    )
```

## -parameters

### -param Mdl [in]


Pointer to an MDL that describes the buffer for which to return the initial virtual address.

## -remarks

**MmGetMdlVirtualAddress** returns the starting virtual address of the MDL.

**MmGetMdlVirtualAddress** returns a virtual address that is not necessarily valid in the current thread context. Lower-level drivers should not attempt to use the returned virtual address to access memory, particularly user memory space.

The returned address, used as an index to a physical address entry in the MDL, can be input to [**MapTransfer**](./nc-wdm-pmap_transfer.md).

Callers of **MmGetMdlVirtualAddress** can be running at any IRQL. Usually, the caller is running at IRQL = DISPATCH_LEVEL because this routine is commonly called to obtain the _CurrentVa_ parameter to **MapTransfer**.
