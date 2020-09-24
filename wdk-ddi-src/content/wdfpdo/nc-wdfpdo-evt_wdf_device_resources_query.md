---
UID: NC:wdfpdo.EVT_WDF_DEVICE_RESOURCES_QUERY
title: EVT_WDF_DEVICE_RESOURCES_QUERY (wdfpdo.h)
description: A bus driver's EvtDeviceResourcesQuery event callback function creates a resource list that represents a specified device's boot configuration.
old-location: wdf\evtdeviceresourcesquery.htm
tech.root: wdf
ms.assetid: 3210b28b-cbaa-4ad9-9ca8-3b5f03aee41e
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_RESOURCES_QUERY callback function"]
ms.keywords: DFDeviceObjectFdoPdoRef_89ca471c-ee81-4799-9b58-410aedd12f87.xml, EVT_WDF_DEVICE_RESOURCES_QUERY, EVT_WDF_DEVICE_RESOURCES_QUERY callback, EvtDeviceResourcesQuery, EvtDeviceResourcesQuery callback function, kmdf.evtdeviceresourcesquery, wdf.evtdeviceresourcesquery, wdfpdo/EvtDeviceResourcesQuery
req.header: wdfpdo.h
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
 - EVT_WDF_DEVICE_RESOURCES_QUERY
 - wdfpdo/EVT_WDF_DEVICE_RESOURCES_QUERY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfpdo.h
api_name:
 - EvtDeviceResourcesQuery
---

# EVT_WDF_DEVICE_RESOURCES_QUERY callback function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

A bus driver's <i>EvtDeviceResourcesQuery</i> event callback function creates a resource list that represents a specified device's <a href="/windows-hardware/drivers/kernel/hardware-resources">boot configuration</a>.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

### -param Resources 

[in]
A handle to a framework resource-list object that represents an empty resource list.

## -returns

If the driver did not encounter any errors, it must return STATUS_SUCCESS (whether or not it specifies boot configuration resources). If the driver encounters errors, it must return an NTSTATUS value that <a href="/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a> evaluates as <b>FALSE</b>.

 

For more information about this callback function's return values, see <a href="/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.

## -remarks

Framework-based bus drivers can provide an <i>EvtDeviceResourcesQuery</i> callback function. To register this callback function, bus drivers call <a href="/windows-hardware/drivers/ddi/wdfpdo/nf-wdfpdo-wdfpdoinitseteventcallbacks">WdfPdoInitSetEventCallbacks</a>.

The framework calls the bus driver's <i>EvtDeviceResourcesQuery</i> callback function to obtain a <a href="/windows-hardware/drivers/kernel/hardware-resources">resource list</a> that specifies the boot configuration for the device. 

The driver must populate the supplied resource list object with hardware resources that represent the boot requirements for the device. Drivers for PnP devices obtain this requirements information from the system BIOS.

To create a resource list, the driver calls <a href="/windows-hardware/drivers/ddi/wdfresource/">framework resource-list object methods</a> that add resources to the resource-list object that is represented by the <i>Resources</i> parameter.For more information about hardware resources and creating resource lists, see <a href="/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfpdo/nc-wdfpdo-evt_wdf_device_resource_requirements_query">EvtDeviceResourceRequirementsQuery</a>