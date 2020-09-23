---
UID: NC:wdffdo.EVT_WDF_DEVICE_REMOVE_ADDED_RESOURCES
title: EVT_WDF_DEVICE_REMOVE_ADDED_RESOURCES (wdffdo.h)
description: A driver's EvtDeviceRemoveAddedResources event callback function removes hardware resources that the driver's EvtDeviceFilterAddResourceRequirements callback function added.
old-location: wdf\evtdeviceremoveaddedresources.htm
tech.root: wdf
ms.assetid: b18c2b34-db6d-4553-9340-556da1fd7991
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_REMOVE_ADDED_RESOURCES callback function"]
ms.keywords: DFDeviceObjectFdoPdoRef_c1020fff-8895-4ece-ae27-ef33d3a65de6.xml, EVT_WDF_DEVICE_REMOVE_ADDED_RESOURCES, EVT_WDF_DEVICE_REMOVE_ADDED_RESOURCES callback, EvtDeviceRemoveAddedResources, EvtDeviceRemoveAddedResources callback function, kmdf.evtdeviceremoveaddedresources, wdf.evtdeviceremoveaddedresources, wdffdo/EvtDeviceRemoveAddedResources
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
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_WDF_DEVICE_REMOVE_ADDED_RESOURCES
 - wdffdo/EVT_WDF_DEVICE_REMOVE_ADDED_RESOURCES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdffdo.h
api_name:
 - EvtDeviceRemoveAddedResources
---

# EVT_WDF_DEVICE_REMOVE_ADDED_RESOURCES callback function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtDeviceRemoveAddedResources</i> event callback function removes hardware resources that the driver's <a href="/windows-hardware/drivers/ddi/wdffdo/nc-wdffdo-evt_wdf_device_filter_resource_requirements">EvtDeviceFilterAddResourceRequirements</a> callback function added.

## -parameters

### -param Device 

[in]
A handle to the framework device object to which resources will be assigned.

### -param ResourcesRaw 

[in]
A handle to a resource list object that identifies the raw hardware resources that the PnP manager has assigned to the device.

### -param ResourcesTranslated 

[in]
A handle to a resource list object that identifies the translated hardware resources that the PnP manager has assigned to the device.

## -returns

If the driver encountered no errors it must return STATUS_SUCCESS. Otherwise it must return an NTSTATUS value that <a href="/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a> evaluates as <b>FALSE</b>.

For more information about return values, see <a href="/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.

## -remarks

Framework-based function drivers can provide an <i>EvtDeviceRemoveAddedResources</i> callback function. To register this callback function, drivers call <a href="/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitseteventcallbacks">WdfFdoInitSetEventCallbacks</a>.

If a driver provides an <a href="/windows-hardware/drivers/ddi/wdffdo/nc-wdffdo-evt_wdf_device_filter_resource_requirements">EvtDeviceFilterAddResourceRequirements</a> callback function that adds resources to a device's hardware requirements list, the driver must also provide an <i>EvtDeviceRemoveAddedResources</i> callback function. The <i>EvtDeviceRemoveAddedResources</i> callback function examines the resource list that the PnP manager has assigned to the device, and removes the resources from the list that the <i>EvtDeviceFilterAddResourceRequirements</i> callback function added. If the driver removes a resource, it must remove it from both the raw and translated resource lists.

For more information about resource lists and the order in which the resources appear, see <a href="/windows-hardware/drivers/wdf/raw-and-translated-resources">raw and translated hardware resources</a>.

The framework calls the driver's <i>EvtDeviceRemoveAddedResources</i> callback function immediately before it passes the device's resource list to the bus driver. This callback function removes added resources so that the bus driver will not attempt to use them. 

For more information about the <i>EvtDeviceRemoveAddedResources</i> callback function, see <a href="/windows-hardware/drivers/wdf/modifying-a-resource-list">Modifying a Resource List</a>.

For more information about hardware resources, see <a href="/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdffdo/nc-wdffdo-evt_wdf_device_filter_resource_requirements">EvtDeviceFilterAddResourceRequirements</a>



<a href="/windows-hardware/drivers/ddi/wdffdo/nc-wdffdo-evt_wdf_device_filter_resource_requirements">EvtDeviceFilterRemoveResourceRequirements</a>