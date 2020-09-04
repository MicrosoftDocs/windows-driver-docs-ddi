---
UID: NS:wdm._IO_RESOURCE_REQUIREMENTS_LIST
title: _IO_RESOURCE_REQUIREMENTS_LIST (wdm.h)
description: The IO_RESOURCE_REQUIREMENTS_LIST structure describes sets of resource configurations that can be used by a device. Each configuration represents a range of raw resources, of various types, that can be used by a device.
old-location: kernel\io_resource_requirements_list.htm
tech.root: kernel
ms.assetid: e581fd34-4564-4882-b91d-94801e579bde
ms.date: 04/30/2018
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
 - IO_RESOURCE_REQUIREMENTS_LIST
---

# _IO_RESOURCE_REQUIREMENTS_LIST structure


## -description

The <b>IO_RESOURCE_REQUIREMENTS_LIST</b> structure describes sets of resource configurations that can be used by a device. Each configuration represents a range of raw resources, of various types, that can be used by a device.

## -struct-fields

### -field ListSize

The total number of bytes that constitute the <b>IO_RESOURCE_REQUIREMENTS_LIST</b> structure, its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_resource_list">IO_RESOURCE_LIST</a> array, and the latter's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_resource_descriptor">IO_RESOURCE_DESCRIPTOR</a> array.

### -field InterfaceType

Specifies an interface type. This must be one of the types defined by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_interface_type">INTERFACE_TYPE</a>, in Wdm.h or Ntddk.h. (Not used by WDM drivers.)

### -field BusNumber

A system-assigned, zero-based bus number. (Not used by WDM drivers.)

### -field SlotNumber

A system slot number. (Not used by WDM drivers.)

### -field Reserved

Not used.

### -field AlternativeLists

The number of alternative lists (or configurations) of hardware resources that are described by this <b>IO_RESOURCE_REQUIREMENTS_LIST</b> structure. The <b>List</b> member is the header for the first alternative list.

### -field List

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_resource_list">IO_RESOURCE_LIST</a> structure that serves as the header for the first alternative list of hardware resources. If the <b>IO_RESOURCE_REQUIREMENTS_LIST</b> structure describes more than one alternative list, the second alternative list immediately follows the first alternative list in memory, and so on. The size of each alternative list depends on the length of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_resource_descriptor">IO_RESOURCE_DESCRIPTOR</a> array that it contains. For more information, see the following Remarks section.

## -remarks

This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-filter-resource-requirements">IRP_MN_FILTER_RESOURCE_REQUIREMENTS</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-resource-requirements">IRP_MN_QUERY_RESOURCE_REQUIREMENTS</a> IRPs to describe one or more alternative configurations of <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/hardware-resources">hardware resources</a>.

The <b>IO_RESOURCE_REQUIREMENTS_LIST</b> structure is a header for a larger data structure, of variable size, that specifies one or more alternative lists of resources. All of the data in this larger structure occupies a contiguous block of memory, whose size is specified by the <b>ListSize</b> member. Each alternative list occupies a subblock within the larger block.

Each alternative list begins with an <b>IO_RESOURCE_LIST</b> structure, which serves as a header for an array of <b>IO_RESOURCE_DESCRIPTOR</b> structures. The length of this array determines the size of the list, which can vary from one alternative list to the next. Driver code can use pointer arithmetic to step from one alternative list to the next. For example, if a parameter named <i>list</i> is a pointer to the <b>IO_RESOURCE_LIST</b> structure at the start of one alternative list, <i>list</i> can be updated to point to the start of the next list as follows:


```cpp
    list = (PIO_RESOURCE_LIST)(list->Descriptors + list->Count);
```

In this example, <code>list->Descriptors</code> is a pointer to the start of the <b>IO_RESOURCE_DESCRIPTOR</b> array, and <code>list->Count</code> is the number of elements in the array. For more information about the <b>Descriptors</b> and <b>Count</b> members, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_resource_list">IO_RESOURCE_LIST</a>.


#### Examples

If a driver contains a handler for an <b>IRP_MN_FILTER_RESOURCE_REQUIREMENTS</b> IRP, the handler typically walks the resource list that is pointed to by the <b>IoStatus.Information</b> field in the IRP. The following code example contains a function—named FilterResources—that is called in the handler to walk the list. This function either verifies that a particular resource is specified in the list, or changes the resource requirements in the list without changing the size of the list. (A function that changes the size of the list would need to allocate a buffer for the updated list, write the list to this buffer, update the <b>IoStatus.Information</b> field in the IRP to point to the updated list, and free the buffer that contains the original list.)

The FilterResources function returns <b>TRUE</b> (probably from the <b>switch</b> statement, although the details are omitted to simplify the code example) if it finds the resource that it is looking for in the list, or if it makes a change to the list that does not change the size of the list. Otherwise, it returns <b>FALSE</b>.


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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_resource_descriptor">IO_RESOURCE_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_resource_list">IO_RESOURCE_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-filter-resource-requirements">IRP_MN_FILTER_RESOURCE_REQUIREMENTS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-resource-requirements">IRP_MN_QUERY_RESOURCE_REQUIREMENTS</a>

