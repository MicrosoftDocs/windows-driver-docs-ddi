---
UID: NF:wdfresource.WdfIoResourceListRemoveByDescriptor
title: WdfIoResourceListRemoveByDescriptor function (wdfresource.h)
description: The WdfIoResourceListRemoveByDescriptor method removes a resource descriptor from a resource requirement list's logical configuration.
old-location: wdf\wdfioresourcelistremovebydescriptor.htm
tech.root: wdf
ms.assetid: c4968449-eba0-4f7a-98e6-6955d3333495
ms.date: 02/26/2018
keywords: ["WdfIoResourceListRemoveByDescriptor function"]
ms.keywords: DFResourceObjectRef_4bd88d52-ea6d-43c1-9477-8338e6bf1cdb.xml, WdfIoResourceListRemoveByDescriptor, WdfIoResourceListRemoveByDescriptor method, kmdf.wdfioresourcelistremovebydescriptor, wdf.wdfioresourcelistremovebydescriptor, wdfresource/WdfIoResourceListRemoveByDescriptor
f1_keywords:
 - "wdfresource/WdfIoResourceListRemoveByDescriptor"
 - "WdfIoResourceListRemoveByDescriptor"
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
- WdfIoResourceListRemoveByDescriptor
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoResourceListRemoveByDescriptor function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfIoResourceListRemoveByDescriptor</b> method removes a resource descriptor from a resource requirement list's <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/hardware-resources">logical configuration</a>.


## -parameters




### -param ResourceList [in]

A handle to a framework resource-range-list object that represents a logical configuration of hardware resources for a device.


### -param Descriptor [in]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_resource_descriptor">IO_RESOURCE_DESCRIPTOR</a> structure that describes a hardware resource.


## -remarks

A bug check occurs if the driver supplies an invalid object handle.




The <b>WdfIoResourceListRemoveByDescriptor</b> method removes the resource descriptor that matches the <i>Descriptor</i> parameter. To find a match, the method compares the specified resource descriptor with the resource descriptors in the logical configuration, byte for byte.

When <b>WdfIoResourceListRemoveByDescriptor</b> removes the resource descriptor that has the index value <i>n</i>, the index value of the next resource descriptor changes from <i>n</i>+1 to <i>n</i>.

For more information about resource requirements lists and logical configurations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


#### Examples

The following code example searches a logical configuration for a resource descriptor that contains a specified port address, and it removes that resource descriptor.

```cpp
IO_RESOURCE_DESCRIPTOR descriptor;
ULONG resCount, j;

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
    // Stop if this descriptor is the port descriptor that
    // we're looking for, and remove the descriptor.
    //
    if (descriptor->Type == CmResourceTypePort) {
        if ((descriptor->u.port.MinimumAddress) == PORT_RANGE_A) {
               WdfIoResourceListRemoveByDescriptor(
                                                   Reslist,
                                                   descriptor
                                                   );
               break;
        }
    }
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_resource_descriptor">IO_RESOURCE_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfresource/nf-wdfresource-wdfioresourcelistremove">WdfIoResourceListRemove</a>
 

 

