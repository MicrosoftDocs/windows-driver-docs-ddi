---
UID: NC:wdffdo.EVT_WDF_DEVICE_FILTER_RESOURCE_REQUIREMENTS
title: EVT_WDF_DEVICE_FILTER_RESOURCE_REQUIREMENTS (wdffdo.h)
description: A driver's EvtDeviceFilterAddResourceRequirements event callback function can add resources to a set of hardware resource requirements before the system assigns resources to a device.
old-location: wdf\evtdevicefilteraddresourcerequirements.htm
tech.root: wdf
ms.assetid: 7d9b38b5-989d-45a3-8771-57a8d1f98725
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_FILTER_RESOURCE_REQUIREMENTS callback function"]
ms.keywords: DFDeviceObjectFdoPdoRef_7a176cba-5c3b-42b7-81e5-0a6a9b49f55c.xml, EVT_WDF_DEVICE_FILTER_RESOURCE_REQUIREMENTS, EVT_WDF_DEVICE_FILTER_RESOURCE_REQUIREMENTS callback, EvtDeviceFilterXxxResourceRequirements, EvtDeviceFilterXxxResourceRequirements callback function, kmdf.evtdevicefilteraddresourcerequirements, wdf.evtdevicefilteraddresourcerequirements, wdf.evtdevicefilterremoveresourcerequirements, wdffdo/EvtDeviceFilterXxxResourceRequirements
f1_keywords:
 - "wdffdo/EvtDeviceFilterXxxResourceRequirements"
req.header: wdffdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdffdo.h
api_name:
- EvtDeviceFilterXxxResourceRequirements
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_FILTER_RESOURCE_REQUIREMENTS callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtDeviceFilterAddResourceRequirements</i> event callback function can add resources to a set of hardware resource requirements before the system assigns resources to a device.

A driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nc-wdffdo-evt_wdf_device_filter_resource_requirements">EvtDeviceFilterRemoveResourceRequirements</a> event callback function can remove resources from a set of hardware resource requirements before the system assigns resources to a device.


## -parameters




### -param Device [in]

A handle to the framework device object to which resources will be assigned.


### -param IoResourceRequirementsList [in]

A handle to a resource-requirements-list object, which represents the device's <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/hardware-resources">resource requirements list</a>.


## -returns



If the driver encountered no errors it must return STATUS_SUCCESS. Otherwise it must return an NTSTATUS value that <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a> evaluates as <b>FALSE</b>.

For more information about return values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.




## -remarks



Framework-based function drivers can provide an <i>EvtDeviceFilterAddResourceRequirements</i> and an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nc-wdffdo-evt_wdf_device_filter_resource_requirements">EvtDeviceFilterRemoveResourceRequirements</a>callback function. To register these callback functions, drivers call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitseteventcallbacks">WdfFdoInitSetEventCallbacks</a>.

When the framework calls a driver's <i>EvtDeviceFilterAddResourceRequirements</i> callback function, the driver can add resource descriptors to a logical configuration, and it can provide additional logical configurations. These added items represent resources that the function driver requires to make the device operational.

If a driver's <i>EvtDeviceFilterAddResourceRequirements</i> callback function adds items to a device's resource requirements list, and if the PnP manager assigns the resources to the device's requirements list, the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nc-wdffdo-evt_wdf_device_remove_added_resources">EvtDeviceRemoveAddedResources</a> callback function must remove the added resources from the device's resource list.

To add items to or remove items from a resource requirements list, the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfresource/">framework resource-requirements-list object methods</a> and framework resource-range-list object methods, which manipulates the resource-requirements-list object that is represented by the <i>IoResourceRequirementsList</i> parameter. 

For more information about these callback functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/modifying-a-resource-requirements-list">Modifying a Resource Requirements List</a>.

For more information about hardware resources and resource requirements lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nc-wdffdo-evt_wdf_device_remove_added_resources">EvtDeviceRemoveAddedResources</a>
 

 

