---
UID: NF:wdfresource.WdfIoResourceRequirementsListSetSlotNumber
title: WdfIoResourceRequirementsListSetSlotNumber function (wdfresource.h)
description: The WdfIoResourceRequirementsListSetSlotNumber method assigns a slot number to a resource requirements list.
old-location: wdf\wdfioresourcerequirementslistsetslotnumber.htm
tech.root: wdf
ms.assetid: 1dc18c48-2331-4980-b741-59a73d3edaa6
ms.date: 02/26/2018
ms.keywords: DFResourceObjectRef_a4c6729c-ba18-49e0-8e8c-94c70c5c9e8a.xml, WdfIoResourceRequirementsListSetSlotNumber, WdfIoResourceRequirementsListSetSlotNumber method, kmdf.wdfioresourcerequirementslistsetslotnumber, wdf.wdfioresourcerequirementslistsetslotnumber, wdfresource/WdfIoResourceRequirementsListSetSlotNumber
f1_keywords:
 - "wdfresource/WdfIoResourceRequirementsListSetSlotNumber"
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
- WdfIoResourceRequirementsListSetSlotNumber
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoResourceRequirementsListSetSlotNumber function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfIoResourceRequirementsListSetSlotNumber</b> method assigns a slot number to a resource requirements list.


## -parameters




### -param RequirementsList [in]

A handle to a framework resource-requirements-list object that represents a device's resource requirements list.


### -param SlotNumber [in]

A value that identifies the bus slot number to which the device is connected.


## -remarks

A bug check occurs if the driver supplies an invalid object handle.




Your driver must provide a slot number if your device does not support Plug and Play (PnP). 

For more information about resource requirements lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


#### Examples

The following code example shows how an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nc-wdfpdo-evt_wdf_device_resource_requirements_query">EvtDeviceResourceRequirementsQuery</a> callback function for a nonPnP device calls <b>WdfIoResourceRequirementsListSetSlotNumber</b> to assign slot 0 to a device.

```cpp
NTSTATUS
Example_EvtDeviceResourceRequirementsQuery(
    IN WDFDEVICE Device,
    IN WDFIORESREQLIST Requirements
    )
{
...
    WdfIoResourceRequirementsListSetSlotNumber(
                                               Requirements,
                                               0
                                               );
...
}
```


