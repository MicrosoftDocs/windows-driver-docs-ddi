---
UID: NF:wdfresource.WdfIoResourceRequirementsListGetCount
title: WdfIoResourceRequirementsListGetCount function (wdfresource.h)
description: The WdfIoResourceRequirementsListGetCount method returns the number of logical configurations that are contained in a resource requirements list.
old-location: wdf\wdfioresourcerequirementslistgetcount.htm
tech.root: wdf
ms.assetid: 00a79e57-5915-49a3-b11f-223cc93c2e99
ms.date: 02/26/2018
keywords: ["WdfIoResourceRequirementsListGetCount function"]
ms.keywords: DFResourceObjectRef_927d5729-0c1e-4363-9f2d-b5fefba8e2f6.xml, WdfIoResourceRequirementsListGetCount, WdfIoResourceRequirementsListGetCount method, kmdf.wdfioresourcerequirementslistgetcount, wdf.wdfioresourcerequirementslistgetcount, wdfresource/WdfIoResourceRequirementsListGetCount
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
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfIoResourceRequirementsListGetCount
 - wdfresource/WdfIoResourceRequirementsListGetCount
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfIoResourceRequirementsListGetCount
---

# WdfIoResourceRequirementsListGetCount function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfIoResourceRequirementsListGetCount</b> method returns the number of <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/hardware-resources">logical configurations</a> that are contained in a resource requirements list.

## -parameters

### -param RequirementsList 

[in]
A handle to a framework resource-requirements-list object that represents a device's resource requirements list.

## -returns

<b>WdfIoResourceRequirementsListGetCount</b> returns the number of logical configurations that are contained in the resource requirements list.

A system bug check occurs if the driver supplies an invalid object handle.

## -remarks

For more information about resource requirements lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


#### Examples

The following code example shows how an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nc-wdffdo-evt_wdf_device_filter_resource_requirements">EvtDeviceFilterRemoveResourceRequirements</a> callback function can obtain the number of logical configurations that are contained in a resource requirements list.

```cpp
NTSTATUS
Example_EvtDeviceFilterRemoveResourceRequirements(
    IN WDFDEVICE Device,
    IN WDFIORESREQLIST RequirementsList
    )
{    
    ULONG count;

    count = WdfIoResourceRequirementsListGetCount(RequirementsList);
}
```

