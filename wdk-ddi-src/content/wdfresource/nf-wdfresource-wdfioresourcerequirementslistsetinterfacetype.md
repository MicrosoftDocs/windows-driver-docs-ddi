---
UID: NF:wdfresource.WdfIoResourceRequirementsListSetInterfaceType
title: WdfIoResourceRequirementsListSetInterfaceType function (wdfresource.h)
description: The WdfIoResourceRequirementsListSetInterfaceType method assigns a bus type to a resource requirements list.
old-location: wdf\wdfioresourcerequirementslistsetinterfacetype.htm
tech.root: wdf
ms.assetid: c229eb9e-cf1f-43ea-b701-fb8fb6196b40
ms.date: 02/26/2018
ms.keywords: DFResourceObjectRef_3ce545f1-cdad-4ddb-8b65-236461296d21.xml, WdfIoResourceRequirementsListSetInterfaceType, WdfIoResourceRequirementsListSetInterfaceType method, kmdf.wdfioresourcerequirementslistsetinterfacetype, wdf.wdfioresourcerequirementslistsetinterfacetype, wdfresource/WdfIoResourceRequirementsListSetInterfaceType
f1_keywords:
 - "wdfresource/WdfIoResourceRequirementsListSetInterfaceType"
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
- WdfIoResourceRequirementsListSetInterfaceType
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoResourceRequirementsListSetInterfaceType function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfIoResourceRequirementsListSetInterfaceType</b> method assigns a bus type to a resource requirements list. 


## -parameters




### -param RequirementsList [in]

A handle to a framework resource-requirements-list object that represents a device's resource requirements list.


### -param InterfaceType [in]

An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_interface_type">INTERFACE_TYPE</a>-typed value that identifies the type of bus that the device is connected to. 


## -remarks

A bug check occurs if the driver supplies an invalid object handle.




Your driver must provide a bus type if your device does not support Plug and Play (PnP). 

For more information about resource requirements lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


#### Examples

The following code example shows how an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nc-wdfpdo-evt_wdf_device_resource_requirements_query">EvtDeviceResourceRequirementsQuery</a> callback function for a nonPnP device calls <b>WdfIoResourceRequirementsListSetInterfaceType</b> to assign a bus type to a device.

```cpp
NTSTATUS
Example_EvtDeviceResourceRequirementsQuery(
    IN WDFDEVICE Device,
    IN WDFIORESREQLIST Requirements
    )
{
...
    WdfIoResourceRequirementsListSetInterfaceType(
                                                  Requirements,
                                                  Isa
                                                  );
...
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_interface_type">INTERFACE_TYPE</a>
 

 

