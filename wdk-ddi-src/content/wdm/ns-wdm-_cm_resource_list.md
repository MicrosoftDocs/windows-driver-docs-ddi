---
UID: NS:wdm._CM_RESOURCE_LIST
title: _CM_RESOURCE_LIST (wdm.h)
description: The CM_RESOURCE_LIST structure specifies all of the system hardware resources assigned to a device.
tech.root: kernel
ms.date: 01/18/2023
keywords: ["CM_RESOURCE_LIST structure"]
ms.keywords: "*PCM_RESOURCE_LIST, CM_RESOURCE_LIST, CM_RESOURCE_LIST structure [Kernel-Mode Driver Architecture], PCM_RESOURCE_LIST, PCM_RESOURCE_LIST structure pointer [Kernel-Mode Driver Architecture], _CM_RESOURCE_LIST, kernel.cm_resource_list, kstruct_a_29dadb2f-b0d2-41a4-b17e-f69c12b6def6.xml, wdm/CM_RESOURCE_LIST, wdm/PCM_RESOURCE_LIST"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Wudfwdm.h
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
req.typenames: CM_RESOURCE_LIST, *PCM_RESOURCE_LIST
f1_keywords:
 - _CM_RESOURCE_LIST
 - wdm/_CM_RESOURCE_LIST
 - PCM_RESOURCE_LIST
 - wdm/PCM_RESOURCE_LIST
 - CM_RESOURCE_LIST
 - wdm/CM_RESOURCE_LIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _CM_RESOURCE_LIST
 - PCM_RESOURCE_LIST
 - CM_RESOURCE_LIST
---

## -description

The **CM_RESOURCE_LIST** structure specifies all of the system hardware resources assigned to a device.

## -struct-fields

### -field Count

The number of full resource descriptors that are specified by this **CM_RESOURCE_LIST** structure. The **List** member is the header for the first full resource descriptor. For WDM drivers, **Count** is always 1.

### -field List

The [**CM_FULL_RESOURCE_DESCRIPTOR**](./ns-wdm-_cm_full_resource_descriptor.md) structure that serves as the header for the first full resource descriptor. If the **CM_RESOURCE_LIST** structure contains more than one full resource descriptor, the second full resource descriptor immediately follows the first in memory, and so on. The size of each full resource descriptor depends on the length of the [**CM_PARTIAL_RESOURCE_DESCRIPTOR**](./ns-wdm-_cm_partial_resource_descriptor.md) array that it contains. For more information, see the following Remarks section.

## -remarks

This structure describes the assignment of hardware resources to a device. An [IRP_MN_START_DEVICE](/windows-hardware/drivers/kernel/irp-mn-start-device) IRP uses this structure to specify the resources that the Plug and Play manager assigns to a device. Drivers for legacy devices use this structure to pass their resource requirements to the [IoReportResourceForDetection](../ntddk/nf-ntddk-ioreportresourcefordetection.md) routine. For more information about hardware resource allocation, see [Hardware Resources](/windows-hardware/drivers/kernel/hardware-resources).

The **CM_RESOURCE_LIST** structure is a header for a larger data structure, of variable size, that contains one or more full resource descriptors. All of the data in this larger structure occupies a contiguous block of memory. Each full resource descriptor occupies a subblock within the larger block.

A full resource descriptor begins with a [**CM_FULL_RESOURCE_DESCRIPTOR**](./ns-wdm-_cm_full_resource_descriptor.md) structure, which serves as a header for an array of [**CM_PARTIAL_RESOURCE_DESCRIPTOR**](./ns-wdm-_cm_partial_resource_descriptor.md) structures. The length of this array determines the size of the full resource descriptor. The last member in the **CM_FULL_RESOURCE_DESCRIPTOR** structure is a [**CM_PARTIAL_RESOURCE_LIST**](./ns-wdm-_cm_partial_resource_list.md) structure that contains, as its last member, the first element in this array. If the array contains more than one element, the remaining elements immediately follow, in memory, the end of the **CM_PARTIAL_RESOURCE_LIST** structure, which is also the end of the **CM_FULL_RESOURCE_DESCRIPTOR** structure.

Driver code can use pointer arithmetic to step from one full resource descriptor to the next. For example, if a parameter named *list* is a pointer to the **CM_FULL_RESOURCE_DESCRIPTOR** structure at the start of one full resource descriptor, *list* can be updated to point to the start of the next full resource descriptor as follows:

```cpp
list = (PCM_FULL_RESOURCE_DESCRIPTOR)(list->PartialResourceList.PartialDescriptors +
                                        list->PartialResourceList.Count);
```

In this example, `list->PartialResourceList.PartialDescriptors` is a pointer to the start of the **CM_PARTIAL_RESOURCE_DESCRIPTOR** array, and `list->PartialResourceList.Count` is the number of elements in the array. For more information about the **PartialDescriptors** and **Count** members, see [**CM_PARTIAL_RESOURCE_LIST**](./ns-wdm-_cm_partial_resource_list.md).

### Examples

All PnP drivers must handle [IRP_MN_START_DEVICE](/windows-hardware/drivers/kernel/irp-mn-start-device) IRPs. Typically, a driver's handler for this IRP walks the lists of assigned resources that are pointed to by the **Parameters.StartDevice.AllocatedResources** and **Parameters.StartDevice.AllocatedResourcesTranslated** members of the [**IO_STACK_LOCATION**](./ns-wdm-_io_stack_location.md) structure in the IRP. The following code example contains a function—named GetAssignedResources—that is called in the handler to walk each list. This function verifies that the required resources are specified in the list, and configures the device to use the resources.

The GetAssignedResources function returns **TRUE** if it succeeds. Otherwise, it returns **FALSE** (probably from the **switch** statement, although the details are omitted to simplify the code example).

```cpp
/* Process the assigned hardware resources. */

BOOLEAN GetAssignedResources(PCM_RESOURCE_LIST reslist)
{
    PCM_FULL_RESOURCE_DESCRIPTOR list;

    list = reslist->List;

    for (int ix = 0; ix < reslist->Count; ++ix)
    {
        /* Process resources in CM_FULL_RESOURCE_DESCRIPTOR block number ix. */

        for (int jx = 0; jx < list->PartialResourceList.Count; ++jx)
        {
            PCM_PARTIAL_RESOURCE_DESCRIPTOR desc;

            desc = list->PartialResourceList.PartialDescriptors + jx;

            switch (desc->Type)
            {
                /* Process element jx in PartialDescriptors array. */

                ...

            }
        }

        /* Advance to next CM_FULL_RESOURCE_DESCRIPTOR block in memory. */

        list = (PCM_FULL_RESOURCE_DESCRIPTOR)(list->PartialResourceList.PartialDescriptors + 
                                              list->PartialResourceList.Count);
    }

    return TRUE;
}
```

## -see-also

[**CM_FLOPPY_DEVICE_DATA**](./ns-wdm-_cm_floppy_device_data.md)

[**CM_FULL_RESOURCE_DESCRIPTOR**](./ns-wdm-_cm_full_resource_descriptor.md)

[**CM_KEYBOARD_DEVICE_DATA**](./ns-wdm-_cm_keyboard_device_data.md)

[**CM_PARTIAL_RESOURCE_LIST**](./ns-wdm-_cm_partial_resource_list.md)

[**CM_RESOURCE_LIST**]()

[**CM_SCSI_DEVICE_DATA**](./ns-wdm-_cm_scsi_device_data.md)

[**CM_SERIAL_DEVICE_DATA**](./ns-wdm-_cm_serial_device_data.md)

[IRP_MN_START_DEVICE](/windows-hardware/drivers/kernel/irp-mn-start-device)

[IoConnectInterrupt](./nf-wdm-ioconnectinterrupt.md)

[IoGetDeviceProperty](./nf-wdm-iogetdeviceproperty.md)

[IoReportResourceForDetection](../ntddk/nf-ntddk-ioreportresourcefordetection.md)