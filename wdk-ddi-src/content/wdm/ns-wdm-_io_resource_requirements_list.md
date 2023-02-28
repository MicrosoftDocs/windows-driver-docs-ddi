---
UID: NS:wdm._IO_RESOURCE_REQUIREMENTS_LIST
title: _IO_RESOURCE_REQUIREMENTS_LIST (wdm.h)
description: The _IO_RESOURCE_REQUIREMENTS_LIST structure (wdm.h) describes sets of resource configurations representing  raw resource types used by a device.
tech.root: kernel
ms.date: 01/18/2023
keywords: ["IO_RESOURCE_REQUIREMENTS_LIST structure"]
ms.keywords: "*PIO_RESOURCE_REQUIREMENTS_LIST, IO_RESOURCE_REQUIREMENTS_LIST, IO_RESOURCE_REQUIREMENTS_LIST structure [Kernel-Mode Driver Architecture], PIO_RESOURCE_REQUIREMENTS_LIST, PIO_RESOURCE_REQUIREMENTS_LIST structure pointer [Kernel-Mode Driver Architecture], _IO_RESOURCE_REQUIREMENTS_LIST, kernel.io_resource_requirements_list, kstruct_b_3a1f163a-5841-4284-9ee7-c0999e1a9bbc.xml, wdm/IO_RESOURCE_REQUIREMENTS_LIST, wdm/PIO_RESOURCE_REQUIREMENTS_LIST"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Miniport.h
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
req.typenames: IO_RESOURCE_REQUIREMENTS_LIST, *PIO_RESOURCE_REQUIREMENTS_LIST
f1_keywords:
 - _IO_RESOURCE_REQUIREMENTS_LIST
 - wdm/_IO_RESOURCE_REQUIREMENTS_LIST
 - PIO_RESOURCE_REQUIREMENTS_LIST
 - wdm/PIO_RESOURCE_REQUIREMENTS_LIST
 - IO_RESOURCE_REQUIREMENTS_LIST
 - wdm/IO_RESOURCE_REQUIREMENTS_LIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _IO_RESOURCE_REQUIREMENTS_LIST
 - PIO_RESOURCE_REQUIREMENTS_LIST
 - IO_RESOURCE_REQUIREMENTS_LIST
---

## -description

The **IO_RESOURCE_REQUIREMENTS_LIST** structure describes sets of resource configurations that can be used by a device. Each configuration represents a range of raw resources, of various types, that can be used by a device.

## -struct-fields

### -field ListSize

The total number of bytes that constitute the **IO_RESOURCE_REQUIREMENTS_LIST** structure, its [IO_RESOURCE_LIST](./ns-wdm-_io_resource_list.md) array, and the latter's [IO_RESOURCE_DESCRIPTOR](./ns-wdm-_io_resource_descriptor.md) array.

### -field InterfaceType

Specifies an interface type. This must be one of the types defined by [INTERFACE_TYPE](./ne-wdm-_interface_type.md), in Wdm.h or Ntddk.h. (Not used by WDM drivers.)

### -field BusNumber

A system-assigned, zero-based bus number. (Not used by WDM drivers.)

### -field SlotNumber

A system slot number. (Not used by WDM drivers.)

### -field Reserved

Reserved.

### -field AlternativeLists

The number of alternative lists (or configurations) of hardware resources that are described by this **IO_RESOURCE_REQUIREMENTS_LIST** structure. The **List** member is the header for the first alternative list.

### -field List

The [**IO_RESOURCE_LIST**](./ns-wdm-_io_resource_list.md) structure that serves as the header for the first alternative list of hardware resources. If the **IO_RESOURCE_REQUIREMENTS_LIST** structure describes more than one alternative list, the second alternative list immediately follows the first alternative list in memory, and so on. The size of each alternative list depends on the length of the [**IO_RESOURCE_DESCRIPTOR**](./ns-wdm-_io_resource_descriptor.md) array that it contains. For more information, see the following Remarks section.

## -remarks

This structure is used by the [IRP_MN_FILTER_RESOURCE_REQUIREMENTS](/windows-hardware/drivers/kernel/irp-mn-filter-resource-requirements) and [IRP_MN_QUERY_RESOURCE_REQUIREMENTS](/windows-hardware/drivers/kernel/irp-mn-query-resource-requirements) IRPs to describe one or more alternative configurations of [hardware resources](/windows-hardware/drivers/kernel/hardware-resources).

The **IO_RESOURCE_REQUIREMENTS_LIST** structure is a header for a larger data structure, of variable size, that specifies one or more alternative lists of resources. All of the data in this larger structure occupies a contiguous block of memory, whose size is specified by the **ListSize** member. Each alternative list occupies a subblock within the larger block.

Each alternative list begins with an **IO_RESOURCE_LIST** structure, which serves as a header for an array of **IO_RESOURCE_DESCRIPTOR** structures. The length of this array determines the size of the list, which can vary from one alternative list to the next. Driver code can use pointer arithmetic to step from one alternative list to the next. For example, if a parameter named *list* is a pointer to the **IO_RESOURCE_LIST** structure at the start of one alternative list, *list* can be updated to point to the start of the next list as follows:

```cpp
list = (PIO_RESOURCE_LIST)(list->Descriptors + list->Count);
```

In this example, `list->Descriptors` is a pointer to the start of the **IO_RESOURCE_DESCRIPTOR** array, and `list->Count` is the number of elements in the array. For more information about the **Descriptors** and **Count** members, see [IO_RESOURCE_LIST](./ns-wdm-_io_resource_list.md).

### Examples

If a driver contains a handler for an **IRP_MN_FILTER_RESOURCE_REQUIREMENTS** IRP, the handler typically walks the resource list that is pointed to by the **IoStatus.Information** field in the IRP. The following code example contains a function—named FilterResources—that is called in the handler to walk the list. This function either verifies that a particular resource is specified in the list, or changes the resource requirements in the list without changing the size of the list. (A function that changes the size of the list would need to allocate a buffer for the updated list, write the list to this buffer, update the **IoStatus.Information** field in the IRP to point to the updated list, and free the buffer that contains the original list.)

The FilterResources function returns **TRUE** (probably from the **switch** statement, although the details are omitted to simplify the code example) if it finds the resource that it is looking for in the list, or if it makes a change to the list that does not change the size of the list. Otherwise, it returns **FALSE**.

```cpp
/* Modify the resource list in place (without changing its size). */

BOOLEAN FilterResources(PIO_RESOURCE_REQUIREMENTS_LIST reqlist)
{
    PIO_RESOURCE_LIST list;

    list = reqlist->List;

    for (int ix = 0; ix < reqlist->AlternativeLists; ++ix)
    {
        /* Process resources in IO_RESOURCE_LIST block number ix. */

        for (int jx = 0; jx < list->Count; ++jx)
        {
            PIO_RESOURCE_DESCRIPTOR desc; 

            desc = list->Descriptors + jx;

            switch (desc->Type)
            {
               /* Process element jx in Descriptors array. */

               ...

            }
        }

        /* Advance to next IO_RESOURCE_LIST block in memory. */

        list = (PIO_RESOURCE_LIST)(list->Descriptors + list->Count);
    }

    return FALSE;
}
```

## -see-also

[**IO_RESOURCE_DESCRIPTOR**](./ns-wdm-_io_resource_descriptor.md)

[**IO_RESOURCE_LIST**](./ns-wdm-_io_resource_list.md)

[IRP_MN_FILTER_RESOURCE_REQUIREMENTS](/windows-hardware/drivers/kernel/irp-mn-filter-resource-requirements)

[IRP_MN_QUERY_RESOURCE_REQUIREMENTS](/windows-hardware/drivers/kernel/irp-mn-query-resource-requirements)