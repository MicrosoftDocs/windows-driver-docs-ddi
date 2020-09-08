---
UID: NC:wdfpdo.EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY
title: EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY (wdfpdo.h)
description: A bus driver's EvtDeviceResourceRequirementsQuery event callback function creates a resource requirements list that represents the device's required hardware resources.
old-location: wdf\evtdeviceresourcerequirementsquery.htm
tech.root: wdf
ms.assetid: bacd7e7c-9f71-4dda-98ed-a8d813360943
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY callback function"]
ms.keywords: DFDeviceObjectFdoPdoRef_7b6a59e4-0131-45fc-9a9b-f9e2c39660a6.xml, EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY, EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY callback, EvtDeviceResourceRequirementsQuery, EvtDeviceResourceRequirementsQuery callback function, kmdf.evtdeviceresourcerequirementsquery, wdf.evtdeviceresourcerequirementsquery, wdfpdo/EvtDeviceResourceRequirementsQuery
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
 - EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY
 - wdfpdo/EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfpdo.h
api_name:
 - EvtDeviceResourceRequirementsQuery
---

# EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY callback function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

A bus driver's <i>EvtDeviceResourceRequirementsQuery</i> event callback function creates a resource requirements list that represents the device's required hardware resources.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

### -param IoResourceRequirementsList 

[in]
A handle to a framework resource-requirements-list object that represents an empty resource requirements list.

## -returns

If the driver did not encounter any errors, it must return STATUS_SUCCESS (whether or not it specifies any required hardware resource). If the driver encounters errors, it must return an NTSTATUS value that <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a> evaluates as <b>FALSE</b>.

 

For more information about this callback function's return values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.

## -remarks

Framework-based bus drivers can provide an <i>EvtDeviceResourceRequirementsQuery</i> callback function. To register this callback function, bus drivers call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nf-wdfpdo-wdfpdoinitseteventcallbacks">WdfPdoInitSetEventCallbacks</a>.

The framework calls the bus driver's <i>EvtDeviceResourceRequirementsQuery</i> callback function to obtain a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/hardware-resources">resource requirements list</a> for the device.

The driver must populate the supplied resource-requirements-list object with logical configurations of hardware resources that will allow the device to operate properly.

To create a resource requirements list, the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfresource/">framework resource-range-list object methods</a>, which add resource descriptors to logical configurations, and framework resource-requirements-list object methods, which add logical configurations to the resource requirements list.

For more information about hardware resources and creating resource requirements lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.

If a driver is running on an operating system version that is earlier than Windows 7, a bus driver can use <i>EvtDeviceResourceRequirementsQuery</i> to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetdevicepropertydata">set a device property</a> on a child device prior to enumerating the child.

To <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetdevicepropertydata">set a device property</a> on Windows 7 or later, a bus driver can  <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/preprocessing-and-postprocessing-irps">provide  a preprocess routine</a> for  <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-device-enumerated">IRP_MN_DEVICE_ENUMERATED</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nc-wdfpdo-evt_wdf_device_resources_query">EvtDeviceResourcesQuery</a>

