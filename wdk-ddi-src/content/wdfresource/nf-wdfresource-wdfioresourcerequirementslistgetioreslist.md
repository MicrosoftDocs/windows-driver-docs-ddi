---
UID: NF:wdfresource.WdfIoResourceRequirementsListGetIoResList
title: WdfIoResourceRequirementsListGetIoResList function (wdfresource.h)
description: The WdfIoResourceRequirementsListGetIoResList method returns a handle to the framework resource-range-list object that represents a specified logical configuration in a specified resource requirements list.
old-location: wdf\wdfioresourcerequirementslistgetioreslist.htm
tech.root: wdf
ms.assetid: b15c0ccf-0863-4415-b31f-b4217f249feb
ms.date: 02/26/2018
keywords: ["WdfIoResourceRequirementsListGetIoResList function"]
ms.keywords: DFResourceObjectRef_a90ce2a4-5690-49c8-ac63-6ccf89f4e5f3.xml, WdfIoResourceRequirementsListGetIoResList, WdfIoResourceRequirementsListGetIoResList method, kmdf.wdfioresourcerequirementslistgetioreslist, wdf.wdfioresourcerequirementslistgetioreslist, wdfresource/WdfIoResourceRequirementsListGetIoResList
f1_keywords:
 - "wdfresource/WdfIoResourceRequirementsListGetIoResList"
 - "WdfIoResourceRequirementsListGetIoResList"
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
- WdfIoResourceRequirementsListGetIoResList
targetos: Windows
req.typenames: 
---

# WdfIoResourceRequirementsListGetIoResList function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfIoResourceRequirementsListGetIoResList</b> method returns a handle to the framework resource-range-list object that represents a specified <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/hardware-resources">logical configuration</a> in a specified resource requirements list.


## -parameters




### -param RequirementsList [in]

A handle to a framework resource-requirements-list object that represents a device's resource requirements list.


### -param Index [in]

A zero-based value that is used as an index into the resource requirements list that <i>RequirementsList</i> specifies. 


## -returns



<b>WdfIoResourceRequirementsListGetIoResList</b> returns a handle to the framework resource-range-list object that represents the logical configuration that the <i>Index</i> parameter identifies, if the index value is valid. Otherwise, the method returns <b>NULL</b>.

A system bug check occurs if the driver supplies an invalid object handle.




## -remarks



For more information about resource requirements lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.

The following code example searches a device's resource requirements list to find the first resource descriptor that describes an interrupt resource.

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
        reslist = WdfIoResourceRequirementsListGetIoResList(
                                          RequirementsList,
                                          i
                                          );

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
            // Stop if this descriptor is an interrupt descriptor.
            //
            if (descriptor->Type == CmResourceTypeInterrupt) {
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
 

 

