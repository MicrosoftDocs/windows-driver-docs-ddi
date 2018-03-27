---
UID: NC:wdffdo.EVT_WDF_DEVICE_FILTER_RESOURCE_REQUIREMENTS
title: EVT_WDF_DEVICE_FILTER_RESOURCE_REQUIREMENTS
author: windows-driver-content
description: A driver's EvtDeviceFilterAddResourceRequirements event callback function can add resources to a set of hardware resource requirements before the system assigns resources to a device.
old-location: wdf\evtdevicefilteraddresourcerequirements.htm
old-project: wdf
ms.assetid: 7d9b38b5-989d-45a3-8771-57a8d1f98725
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_7a176cba-5c3b-42b7-81e5-0a6a9b49f55c.xml, EVT_WDF_DEVICE_FILTER_RESOURCE_REQUIREMENTS, EvtDeviceFilterXxxResourceRequirements, EvtDeviceFilterXxxResourceRequirements callback function, kmdf.evtdevicefilteraddresourcerequirements, wdf.evtdevicefilteraddresourcerequirements, wdf.evtdevicefilterremoveresourcerequirements, wdffdo/EvtDeviceFilterXxxResourceRequirements
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdffdo.h
api_name:
-	EvtDeviceFilterXxxResourceRequirements
product: Windows
targetos: Windows
req.typenames: WDF_DRIVER_VERSION_AVAILABLE_PARAMS, *PWDF_DRIVER_VERSION_AVAILABLE_PARAMS
req.product: Windows 10 or later.
---

# EVT_WDF_DEVICE_FILTER_RESOURCE_REQUIREMENTS callback


## -description


<p class="CCE_Message">[Applies to KMDF only]

A driver's <i>EvtDeviceFilterAddResourceRequirements</i> event callback function can add resources to a set of hardware resource requirements before the system assigns resources to a device.

A driver's <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff540870">EvtDeviceFilterRemoveResourceRequirements</a> event callback function can remove resources from a set of hardware resource requirements before the system assigns resources to a device.


## -parameters




### -param Device [in]

A handle to the framework device object to which resources will be assigned.


### -param IoResourceRequirementsList [in]

A handle to a resource-requirements-list object, which represents the device's <a href="https://msdn.microsoft.com/c7a6997b-34f9-4dd9-b384-2321a8b5ce54">resource requirements list</a>.


## -returns



If the driver encountered no errors it must return STATUS_SUCCESS. Otherwise it must return an NTSTATUS value that <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a> evaluates as <b>FALSE</b>.

For more information about return values, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.




## -remarks



Framework-based function drivers can provide an <i>EvtDeviceFilterAddResourceRequirements</i> and an <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff540870">EvtDeviceFilterRemoveResourceRequirements</a>callback function. To register these callback functions, drivers call <a href="https://msdn.microsoft.com/library/windows/hardware/ff547268">WdfFdoInitSetEventCallbacks</a>.

When the framework calls a driver's <i>EvtDeviceFilterAddResourceRequirements</i> callback function, the driver can add resource descriptors to a logical configuration, and it can provide additional logical configurations. These added items represent resources that the function driver requires to make the device operational.

If a driver's <i>EvtDeviceFilterAddResourceRequirements</i> callback function adds items to a device's resource requirements list, and if the PnP manager assigns the resources to the device's requirements list, the driver's <a href="https://msdn.microsoft.com/b18c2b34-db6d-4553-9340-556da1fd7991">EvtDeviceRemoveAddedResources</a> callback function must remove the added resources from the device's resource list.

To add items to or remove items from a resource requirements list, the driver calls <a href="https://msdn.microsoft.com/2361CEA9-A58C-4019-B4F6-BA1D7DEE3A80">framework resource-requirements-list object methods</a> and framework resource-range-list object methods, which manipulates the resource-requirements-list object that is represented by the <i>IoResourceRequirementsList</i> parameter. 

For more information about these callback functions, see <a href="https://msdn.microsoft.com/75391dd2-5ae1-4562-97a0-4de21a08b61c">Modifying a Resource Requirements List</a>.

For more information about hardware resources and resource requirements lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


#### Examples

To define an <i>EvtDeviceFilterAddResourceRequirements</i> or <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff540870">EvtDeviceFilterRemoveResourceRequirements</a> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceFilterAddResourceRequirements</i> callback function that is named <i>MyDeviceFilterAddResourceRequirements</i>, use the <b>EVT_WDF_DEVICE_FILTER_RESOURCE_REQUIREMENTS</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_FILTER_RESOURCE_REQUIREMENTS  MyDeviceFilterAddResourceRequirements;</pre>
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
 MyDeviceFilterAddResourceRequirements (
    WDFDEVICE  Device,
    WDFIORESREQLIST  IoResourceRequirementsList
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_FILTER_RESOURCE_REQUIREMENTS</b> function type is defined in the Wdffdo.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_FILTER_RESOURCE_REQUIREMENTS</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/b18c2b34-db6d-4553-9340-556da1fd7991">EvtDeviceRemoveAddedResources</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DEVICE_FILTER_RESOURCE_REQUIREMENTS callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

