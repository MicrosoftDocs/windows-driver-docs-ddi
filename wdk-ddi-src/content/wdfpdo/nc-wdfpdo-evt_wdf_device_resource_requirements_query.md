---
UID: NC:wdfpdo.EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY
title: EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY
author: windows-driver-content
description: A bus driver's EvtDeviceResourceRequirementsQuery event callback function creates a resource requirements list that represents the device's required hardware resources.
old-location: wdf\evtdeviceresourcerequirementsquery.htm
old-project: wdf
ms.assetid: bacd7e7c-9f71-4dda-98ed-a8d813360943
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtdeviceresourcerequirementsquery, EvtDeviceResourceRequirementsQuery callback function, EvtDeviceResourceRequirementsQuery, EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY, EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY, wdfpdo/EvtDeviceResourceRequirementsQuery, DFDeviceObjectFdoPdoRef_7b6a59e4-0131-45fc-9a9b-f9e2c39660a6.xml, kmdf.evtdeviceresourcerequirementsquery
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	Wdfpdo.h
apiname: 
-	EvtDeviceResourceRequirementsQuery
product: Windows
targetos: Windows
req.typenames: WDF_OBJECT_CONTEXT_TYPE_INFO, *PWDF_OBJECT_CONTEXT_TYPE_INFO
req.product: Windows 10 or later.
---

# EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY callback


## -description


<p class="CCE_Message">[Applies to KMDF only]

A bus driver's <i>EvtDeviceResourceRequirementsQuery</i> event callback function creates a resource requirements list that represents the device's required hardware resources.


## -prototype


````
EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY EvtDeviceResourceRequirementsQuery;

NTSTATUS EvtDeviceResourceRequirementsQuery(
  _In_ WDFDEVICE       Device,
  _In_ WDFIORESREQLIST IoResourceRequirementsList
)
{ ... }
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param IoResourceRequirementsList [in]

A handle to a framework resource-requirements-list object that represents an empty resource requirements list.


## -returns


If the driver did not encounter any errors, it must return STATUS_SUCCESS (whether or not it specifies any required hardware resource). If the driver encounters errors, it must return an NTSTATUS value that <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a> evaluates as <b>FALSE</b>.

 

For more information about this callback function's return values, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.





## -remarks


Framework-based bus drivers can provide an <i>EvtDeviceResourceRequirementsQuery</i> callback function. To register this callback function, bus drivers call <a href="..\wdfpdo\nf-wdfpdo-wdfpdoinitseteventcallbacks.md">WdfPdoInitSetEventCallbacks</a>.

The framework calls the bus driver's <i>EvtDeviceResourceRequirementsQuery</i> callback function to obtain a <a href="https://msdn.microsoft.com/c7a6997b-34f9-4dd9-b384-2321a8b5ce54">resource requirements list</a> for the device.

The driver must populate the supplied resource-requirements-list object with logical configurations of hardware resources that will allow the device to operate properly.

To create a resource requirements list, the driver calls <a href="https://msdn.microsoft.com/2361CEA9-A58C-4019-B4F6-BA1D7DEE3A80">framework resource-range-list object methods</a>, which add resource descriptors to logical configurations, and framework resource-requirements-list object methods, which add logical configurations to the resource requirements list.

For more information about hardware resources and creating resource requirements lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.

If a driver is running on an operating system version that is earlier than Windows 7, a bus driver can use <i>EvtDeviceResourceRequirementsQuery</i> to <a href="..\wdm\nf-wdm-iosetdevicepropertydata.md">set a device property</a> on a child device prior to enumerating the child.

To <a href="..\wdm\nf-wdm-iosetdevicepropertydata.md">set a device property</a> on Windows 7 or later, a bus driver can  <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/preprocessing-and-postprocessing-irps">provide  a preprocess routine</a> for  <a href="https://msdn.microsoft.com/library/windows/hardware/hh285209">IRP_MN_DEVICE_ENUMERATED</a>.



## -see-also

<a href="https://msdn.microsoft.com/3210b28b-cbaa-4ad9-9ca8-3b5f03aee41e">EvtDeviceResourcesQuery</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

