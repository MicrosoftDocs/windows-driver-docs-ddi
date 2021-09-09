---
UID: NS:wdm._SCATTER_GATHER_LIST
title: _SCATTER_GATHER_LIST (wdm.h)
description: The SCATTER_GATHER_LIST structure describes the scatter/gather list for a DMA operation.
old-location: kernel\scatter_gather_list.htm
tech.root: kernel
ms.date: 08/03/2021
keywords: ["SCATTER_GATHER_LIST structure"]
ms.keywords: "*PSCATTER_GATHER_LIST, PSCATTER_GATHER_LIST, PSCATTER_GATHER_LIST structure pointer [Kernel-Mode Driver Architecture], SCATTER_GATHER_LIST, SCATTER_GATHER_LIST structure [Kernel-Mode Driver Architecture], _SCATTER_GATHER_LIST, kernel.scatter_gather_list, kstruct_d_b8c13069-6d90-4fcf-8582-c57bf11509ea.xml, wdm/PSCATTER_GATHER_LIST, wdm/SCATTER_GATHER_LIST"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.irql: 
targetos: Windows
req.typenames: SCATTER_GATHER_LIST, *PSCATTER_GATHER_LIST
f1_keywords:
 - _SCATTER_GATHER_LIST
 - wdm/_SCATTER_GATHER_LIST
 - PSCATTER_GATHER_LIST
 - wdm/PSCATTER_GATHER_LIST
 - SCATTER_GATHER_LIST
 - wdm/SCATTER_GATHER_LIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _SCATTER_GATHER_LIST
 - PSCATTER_GATHER_LIST
 - SCATTER_GATHER_LIST
---

# _SCATTER_GATHER_LIST structure

## -description

The **SCATTER_GATHER_LIST** structure describes the scatter/gather list for a DMA operation.

## -struct-fields

### -field NumberOfElements

Specifies the number of elements in the **Elements** array.

### -field Reserved

Reserved for future use.

### -field Elements

Specifies an array of scatter/gather elements that comprise a scatter/gather list. Each array element is a structure of type **SCATTER_GATHER_ELEMENT**, which is defined as follows:

```cpp
typedef struct _SCATTER_GATHER_ELEMENT {
  PHYSICAL_ADDRESS  Address;
  ULONG  Length;
  ULONG_PTR  Reserved;
} SCATTER_GATHER_ELEMENT, *PSCATTER_GATHER_ELEMENT;
```

The **SCATTER_GATHER_ELEMENT** structure specifies the length, in bytes, of a physically contiguous scatter/gather region and the starting physical address of this region.

## -remarks

For a driver that performs scatter/gather DMA, the [GetScatterGatherList](./nc-wdm-pget_scatter_gather_list.md) or [BuildScatterGatherList](./nc-wdm-pbuild_scatter_gather_list.md) routine creates a scatter/gather list and passes this list to the driver's [AdapterListControl](./nc-wdm-driver_list_control.md) routine. This scatter/gather list consists of a **SCATTER_GATHER_LIST** structure that is immediately followed in memory by a **SCATTER_GATHER_ELEMENT** array. The number of elements in this array is specified by the **NumberOfElements** member of the **SCATTER_GATHER_LIST** structure.

For more information about scatter/gather lists, see [Using Scatter/Gather DMA](/windows-hardware/drivers/kernel/using-scatter-gather-dma).

## -see-also

[AdapterListControl](./nc-wdm-driver_list_control.md)

[BuildScatterGatherList](./nc-wdm-pbuild_scatter_gather_list.md)

[GetScatterGatherList](./nc-wdm-pget_scatter_gather_list.md)