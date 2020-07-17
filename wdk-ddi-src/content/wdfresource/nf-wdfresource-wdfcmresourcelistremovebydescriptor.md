---
UID: NF:wdfresource.WdfCmResourceListRemoveByDescriptor
title: WdfCmResourceListRemoveByDescriptor function (wdfresource.h)
description: The WdfCmResourceListRemoveByDescriptor method removes a specified resource descriptor from a specified resource list.
old-location: wdf\wdfcmresourcelistremovebydescriptor.htm
tech.root: wdf
ms.assetid: 532b56c9-6c24-4737-b1d6-e44802a898e3
ms.date: 02/26/2018
keywords: ["WdfCmResourceListRemoveByDescriptor function"]
ms.keywords: DFResourceObjectRef_14bc7eb5-5cf4-49ae-83da-144ba0c9adea.xml, WdfCmResourceListRemoveByDescriptor, WdfCmResourceListRemoveByDescriptor method, kmdf.wdfcmresourcelistremovebydescriptor, wdf.wdfcmresourcelistremovebydescriptor, wdfresource/WdfCmResourceListRemoveByDescriptor
f1_keywords:
 - "wdfresource/WdfCmResourceListRemoveByDescriptor"
 - "WdfCmResourceListRemoveByDescriptor"
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
- WdfCmResourceListRemoveByDescriptor
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfCmResourceListRemoveByDescriptor function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfCmResourceListRemoveByDescriptor</b> method removes a specified resource descriptor from a specified resource list.


## -parameters




### -param List [in]

A handle to a framework resource-list object that represents a list of hardware resources for a device.


### -param Descriptor [in]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure that describes a hardware resource.


## -remarks

A bug check occurs if the driver supplies an invalid object handle.




The <b>WdfCmResourceListRemoveByDescriptor</b> method removes the resource descriptor that matches the <i>Descriptor</i> parameter. To find a match, the method compares the specified resource descriptor with the resource descriptors in the logical configuration, byte for byte.

When <b>WdfCmResourceListRemoveByDescriptor</b> removes the resource descriptor that has the index value <i>n</i>, the index value of the next resource descriptor changes from <i>n</i>+1 to <i>n</i>.

For more information about resource lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


#### Examples

The following code example searches for port resource descriptors in a device's resource lists. For each port resource that the example finds, it checks to see if the port address is within a certain range. If the port address is outside of the range, the example removes the descriptor from both the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/raw-and-translated-resources">raw and translated resource lists</a>.

```cpp
NTSTATUS
MyEvtDeviceRemoveAddedResources(
    WDFDEVICE Device,
    WDFCMRESLIST ResourcesRaw,
    WDFCMRESLIST ResourcesTranslated
    )
{    
    ULONG i, count;

    pDevExt = DeviceGetExtension(Device);
    count = WdfCmResourceListGetCount(ResourcesRaw);

    for (i = 0; i < count; i++) {
        PCM_PARTIAL_RESOURCE_DESCRIPTOR descriptor;

        descriptor = WdfCmResourceListGetDescriptor(
                                                    ResourcesRaw,
                                                    i
                                                    );

        if (descriptor->Type != CmResourceTypePort) {
            continue;
        }

        if (descriptor->u.Port.Start.QuadPart < pDevExt->Ranges[0].MinAddress ||
             descriptor->u.Port.Start.QuadPart > pDevExt->Ranges[0].MaxAddress)
        {
            WdfCmResourceListRemoveByDescriptor(
                                                ResourcesRaw,
                                                descriptor
                                                );

            // The descriptor may not be the same in the raw and translated resource lists, so use an index for the second removal

            WdfCmResourceListRemove(
                                                ResourcesTranslated,
                                                i
                                                );
            break;
        }
    }
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfresource/nf-wdfresource-wdfcmresourcelistremove">WdfCmResourceListRemove</a>
 

 

