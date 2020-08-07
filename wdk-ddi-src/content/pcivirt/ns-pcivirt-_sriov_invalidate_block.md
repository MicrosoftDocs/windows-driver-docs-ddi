---
UID: NS:pcivirt._SRIOV_INVALIDATE_BLOCK
title: _SRIOV_INVALIDATE_BLOCK (pcivirt.h)
description: Contains the configuration block information. This structure is used in a IOCTL_SRIOV_INVALIDATE_BLOCK request.
old-location: pci\sriov_invalidate_block.htm
tech.root: PCI
ms.assetid: 483e6144-9752-4d47-9ed4-7e73bc0a59cc
ms.date: 02/24/2018
keywords: ["SRIOV_INVALIDATE_BLOCK structure"]
ms.keywords: "*PSRIOV_INVALIDATE_BLOCK, PCI.sriov_invalidate_block, SRIOV_INVALIDATE_BLOCK, SRIOV_INVALIDATE_BLOCK structure [Buses], _SRIOV_INVALIDATE_BLOCK, pcivirt/SRIOV_INVALIDATE_BLOCK"
f1_keywords:
 - "pcivirt/SRIOV_INVALIDATE_BLOCK"
 - "SRIOV_INVALIDATE_BLOCK"
req.header: pcivirt.h
req.include-header:
req.target-type: Windows
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
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Pcivirt.h
api_name:
- SRIOV_INVALIDATE_BLOCK
targetos: Windows
req.typenames: SRIOV_INVALIDATE_BLOCK, *PSRIOV_INVALIDATE_BLOCK
---

# _SRIOV_INVALIDATE_BLOCK structure


## -description


Contains the configuration block information. This structure is used in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/ni-pcivirt-ioctl_sriov_invalidate_block">IOCTL_SRIOV_INVALIDATE_BLOCK</a> request.


## -syntax


```cpp
typedef struct _SRIOV_INVALIDATE_BLOCK {
  USHORT  VfIndex;
  UINT64  BlockMask;
} SRIOV_INVALIDATE_BLOCK, SRIOV_INVALIDATE_BLOCK;
```


## -struct-fields




### -field VfIndex

Zero-based index of the virtual function (VF) from the first VF exposed by this physical function (PF).


### -field BlockMask

a block of configuration data.


## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/ni-pcivirt-ioctl_sriov_invalidate_block">IOCTL_SRIOV_INVALIDATE_BLOCK</a>



 

 


