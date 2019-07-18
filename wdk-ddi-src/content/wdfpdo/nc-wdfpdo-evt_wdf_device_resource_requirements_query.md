---
UID: NC:wdfpdo.EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY
title: EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY (wdfpdo.h)
description: A bus driver's EvtDeviceResourceRequirementsQuery event callback function creates a resource requirements list that represents the device's required hardware resources.
old-location: wdf\evtdeviceresourcerequirementsquery.htm
tech.root: wdf
ms.assetid: bacd7e7c-9f71-4dda-98ed-a8d813360943
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_7b6a59e4-0131-45fc-9a9b-f9e2c39660a6.xml, EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY, EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY callback, EvtDeviceResourceRequirementsQuery, EvtDeviceResourceRequirementsQuery callback function, kmdf.evtdeviceresourcerequirementsquery, wdf.evtdeviceresourcerequirementsquery, wdfpdo/EvtDeviceResourceRequirementsQuery
ms.topic: callback
f1_keywords:
 - "wdfpdo/EvtDeviceResourceRequirementsQuery"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfpdo.h
api_name:
- EvtDeviceResourceRequirementsQuery
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

A bus driver's <i>EvtDeviceResourceRequirementsQuery</i> event callback function creates a resource requirements list that represents the device's required hardware resources.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param IoResourceRequirementsList [in]

A handle to a framework resource-requirements-list object that represents an empty resource requirements list.


## -returns



If the driver did not encounter any errors, it must return STATUS_SUCCESS (whether or not it specifies any required hardware resource). If the driver encounters errors, it must return an NTSTATUS value that <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a> evaluates as <b>FALSE</b>.

 

For more information about this callback function's return values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.






## -remarks



Framework-based bus drivers can provide an <i>EvtDeviceResourceRequirementsQuery</i> callback function. To register this callback function, bus drivers call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfpdo/nf-wdfpdo-wdfpdoinitseteventcallbacks">WdfPdoInitSetEventCallbacks</a>.

The framework calls the bus driver's <i>EvtDeviceResourceRequirementsQuery</i> callback function to obtain a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/hardware-resources">resource requirements list</a> for the device.

The driver must populate the supplied resource-requirements-list object with logical configurations of hardware resources that will allow the device to operate properly.

To create a resource requirements list, the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfresource/">framework resource-range-list object methods</a>, which add resource descriptors to logical configurations, and framework resource-requirements-list object methods, which add logical configurations to the resource requirements list.

For more information about hardware resources and creating resource requirements lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.

If a driver is running on an operating system version that is earlier than Windows 7, a bus driver can use <i>EvtDeviceResourceRequirementsQuery</i> to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iosetdevicepropertydata">set a device property</a> on a child device prior to enumerating the child.

To <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iosetdevicepropertydata">set a device property</a> on Windows 7 or later, a bus driver can  <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/preprocessing-and-postprocessing-irps">provide  a preprocess routine</a> for  <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-device-enumerated">IRP_MN_DEVICE_ENUMERATED</a>.


#### Examples

To define an <i>EvtDeviceResourceRequirementsQuery</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceResourceRequirementsQuery</i> callback function that is named <i>MyDeviceResourceRequirementsQuery</i>, use the <b>EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY  MyDeviceResourceRequirementsQuery;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
NTSTATUS
 MyDeviceResourceRequirementsQuery (
    WDFDEVICE  Device,
    WDFIORESREQLIST  IoResourceRequirementsList
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY</b> function type is defined in the Wdfpdo.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfpdo/nc-wdfpdo-evt_wdf_device_resources_query">EvtDeviceResourcesQuery</a>
 

 

