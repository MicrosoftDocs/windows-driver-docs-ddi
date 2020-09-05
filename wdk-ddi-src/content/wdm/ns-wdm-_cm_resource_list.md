---
UID: NS:wdm._CM_RESOURCE_LIST
title: _CM_RESOURCE_LIST (wdm.h)
description: The CM_RESOURCE_LIST structure specifies all of the system hardware resources assigned to a device.
old-location: kernel\cm_resource_list.htm
tech.root: kernel
ms.assetid: 01f31255-a4f7-4a16-9238-a7391bb850d1
ms.date: 04/30/2018
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
 - CM_RESOURCE_LIST
---

# _CM_RESOURCE_LIST structure


## -description

The <b>CM_RESOURCE_LIST</b> structure specifies all of the system hardware resources assigned to a device.

## -struct-fields

### -field Count

The number of full resource descriptors that are specified by this <b>CM_RESOURCE_LIST</b> structure. The <b>List</b> member is the header for the first full resource descriptor. For WDM drivers, <b>Count</b> is always 1.

### -field List

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_full_resource_descriptor">CM_FULL_RESOURCE_DESCRIPTOR</a> structure that serves as the header for the first full resource descriptor. If the <b>CM_RESOURCE_LIST</b> structure contains more than one full resource descriptor, the second full resource descriptor immediately follows the first in memory, and so on. The size of each full resource descriptor depends on the length of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> array that it contains. For more information, see the following Remarks section.

## -remarks

This structure describes the assignment of hardware resources to a device. An <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-start-device">IRP_MN_START_DEVICE</a> IRP uses this structure to specify the resources that the Plug and Play manager assigns to a device. Drivers for legacy devices use this structure to pass their resource requirements to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioreportresourcefordetection">IoReportResourceForDetection</a> routine. For more information about hardware resource allocation, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/hardware-resources">Hardware Resources</a>.

The <b>CM_RESOURCE_LIST</b> structure is a header for a larger data structure, of variable size, that contains one or more full resource descriptors. All of the data in this larger structure occupies a contiguous block of memory. Each full resource descriptor occupies a subblock within the larger block.

A full resource descriptor begins with a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_full_resource_descriptor">CM_FULL_RESOURCE_DESCRIPTOR</a> structure, which serves as a header for an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structures. The length of this array determines the size of the full resource descriptor. The last member in the <b>CM_FULL_RESOURCE_DESCRIPTOR</b> structure is a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_list">CM_PARTIAL_RESOURCE_LIST</a> structure that contains, as its last member, the first element in this array. If the array contains more than one element, the remaining elements immediately follow, in memory, the end of the <b>CM_PARTIAL_RESOURCE_LIST</b> structure, which is also the end of the <b>CM_FULL_RESOURCE_DESCRIPTOR</b> structure.

Driver code can use pointer arithmetic to step from one full resource descriptor to the next. For example, if a parameter named <i>list</i> is a pointer to the <b>CM_FULL_RESOURCE_DESCRIPTOR</b> structure at the start of one full resource descriptor, <i>list</i> can be updated to point to the start of the next full resource descriptor as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>    list = (PCM_FULL_RESOURCE_DESCRIPTOR)(list->PartialResourceList.PartialDescriptors +
                                          list->PartialResourceList.Count);</pre>
</td>
</tr>
</table></span></div>
In this example, <code>list->PartialResourceList.PartialDescriptors</code> is a pointer to the start of the <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b> array, and <code>list->PartialResourceList.Count</code> is the number of elements in the array. For more information about the <b>PartialDescriptors</b> and <b>Count</b> members, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_list">CM_PARTIAL_RESOURCE_LIST</a>.


#### Examples

All PnP drivers must handle <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-start-device">IRP_MN_START_DEVICE</a> IRPs. Typically, a driver's handler for this IRP walks the lists of assigned resources that are pointed to by the <b>Parameters.StartDevice.AllocatedResources</b> and <b>Parameters.StartDevice.AllocatedResourcesTranslated</b> members of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a> structure in the IRP. The following code example contains a function—named GetAssignedResources—that is called in the handler to walk each list. This function verifies that the required resources are specified in the list, and configures the device to use the resources.

The GetAssignedResources function returns <b>TRUE</b> if it succeeds. Otherwise, it returns <b>FALSE</b> (probably from the <b>switch</b> statement, although the details are omitted to simplify the code example).

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>/* Process the assigned hardware resources. */

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
}</pre>
</td>
</tr>
</table></span></div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_floppy_device_data">CM_FLOPPY_DEVICE_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_full_resource_descriptor">CM_FULL_RESOURCE_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_keyboard_device_data">CM_KEYBOARD_DEVICE_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_list">CM_PARTIAL_RESOURCE_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_resource_list">CM_RESOURCE_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_scsi_device_data">CM_SCSI_DEVICE_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_serial_device_data">CM_SERIAL_DEVICE_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-start-device">IRP_MN_START_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioconnectinterrupt">IoConnectInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdeviceproperty">IoGetDeviceProperty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioreportresourcefordetection">IoReportResourceForDetection</a>

