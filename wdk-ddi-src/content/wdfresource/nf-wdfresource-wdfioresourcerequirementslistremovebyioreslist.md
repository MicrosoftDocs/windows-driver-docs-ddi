---
UID: NF:wdfresource.WdfIoResourceRequirementsListRemoveByIoResList
title: WdfIoResourceRequirementsListRemoveByIoResList function (wdfresource.h)
description: The WdfIoResourceRequirementsListRemoveByIoResList method removes a logical configuration from a resource requirements list.
old-location: wdf\wdfioresourcerequirementslistremovebyioreslist.htm
tech.root: wdf
ms.assetid: 507729e9-96da-461c-badb-a3725abf6591
ms.date: 02/26/2018
ms.keywords: DFResourceObjectRef_fa50f423-3ade-4deb-89a0-d79cd3f98710.xml, WdfIoResourceRequirementsListRemoveByIoResList, WdfIoResourceRequirementsListRemoveByIoResList method, kmdf.wdfioresourcerequirementslistremovebyioreslist, wdf.wdfioresourcerequirementslistremovebyioreslist, wdfresource/WdfIoResourceRequirementsListRemoveByIoResList
f1_keywords:
 - "wdfresource/WdfIoResourceRequirementsListRemoveByIoResList"
req.header: wdfresource.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfIoResourceRequirementsListRemoveByIoResList
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoResourceRequirementsListRemoveByIoResList function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfIoResourceRequirementsListRemoveByIoResList</b> method removes a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/hardware-resources">logical configuration</a> from a resource requirements list.


## -parameters




### -param RequirementsList [in]

A handle to a framework resource-requirements-list object that represents a device's resource requirements list.


### -param IoResList [in]

A handle to a framework resource-range-list object that represents the logical configuration to be removed from the resource requirements list that <i>RequirementsList</i> specifies.


## -remarks

A bug check occurs if the driver supplies an invalid object handle.




The <b>WdfIoResourceRequirementsListRemoveByIoResList</b> method removes the logical configuration that is associated with the handle that the <i>IoResList</i> parameter specifies.

When <b>WdfIoResourceRequirementsListRemoveByIoResList</b> removes the logical configuration that has the index value <i>n</i>, the index value of the next logical configuration changes from <i>n</i>+1 to <i>n</i>.

For more information about resource requirements lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


#### Examples

The following code example searches the logical configurations in a device's resource requirements list to find a configuration that contains a specific port address. If the example finds that configuration, it removes the configuration.

```cpp
NTSTATUS
Example_EvtDeviceFilterRemoveResourceRequirements(
    IN WDFDEVICE Device,
    IN WDFIORESREQLIST RequirementsList
    )
{
    ULONG i, j, reqCount, resCount;
    BOOLEAN descriptorFound = FALSE;

    //
    // Obtain the number of logical configurations.
    //
    reqCount = WdfIoResourceRequirementsListGetCount(RequirementsList);

    //
    // Search each logical configuration.
    //
    for (i = 0; i < reqCount; i++) {
        WDFIORESLIST reslist;

        if (descriptorFound) {
            break;
        }
        reslist = WdfIoResourceRequirementsListGetIoResList(RequirementsList, i);

        //
        // Get the number of resource descriptors that
        // are in this logical configuration.
        //
        resCount = WdfIoResourceListGetCount(reslist);

        for (j = 0; j < resCount; j++) {
            PIO_RESOURCE_DESCRIPTOR descriptor;

            //
            // Get the next resource descriptor.
            //
            descriptor = WdfIoResourceListGetDescriptor(
                                 reslist,
                                 j
                                 );

            //
            // Stop if this descriptor is the port descriptor
            // that we're looking for.
            //
            if (descriptor->Type == CmResourceTypePort) {
                if ((descriptor->u.Port.MinimumAddress) == PORT_RANGE_A) {
                    WdfIoResourceRequirementsListRemoveByIoResList(
                                 RequirementsList,
                                 reslist
                                 );
                    descriptorFound = TRUE;
                    break;
            }
        }
    }
...
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_resource_descriptor">IO_RESOURCE_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfresource/nf-wdfresource-wdfioresourcelistgetcount">WdfIoResourceListGetCount</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfresource/nf-wdfresource-wdfioresourcelistgetdescriptor">WdfIoResourceListGetDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfresource/nf-wdfresource-wdfioresourcerequirementslistgetcount">WdfIoResourceRequirementsListGetCount</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfresource/nf-wdfresource-wdfioresourcerequirementslistgetioreslist">WdfIoResourceRequirementsListGetIoResList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfresource/nf-wdfresource-wdfioresourcerequirementslistremove">WdfIoResourceRequirementsListRemove</a>
 

 

