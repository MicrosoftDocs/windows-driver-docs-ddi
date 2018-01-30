---
UID: NC:wdffdo.EVT_WDF_DEVICE_REMOVE_ADDED_RESOURCES
title: EVT_WDF_DEVICE_REMOVE_ADDED_RESOURCES
author: windows-driver-content
description: A driver's EvtDeviceRemoveAddedResources event callback function removes hardware resources that the driver's EvtDeviceFilterAddResourceRequirements callback function added.
old-location: wdf\evtdeviceremoveaddedresources.htm
old-project: wdf
ms.assetid: b18c2b34-db6d-4553-9340-556da1fd7991
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtdeviceremoveaddedresources, EvtDeviceRemoveAddedResources callback function, EvtDeviceRemoveAddedResources, EVT_WDF_DEVICE_REMOVE_ADDED_RESOURCES, EVT_WDF_DEVICE_REMOVE_ADDED_RESOURCES, wdffdo/EvtDeviceRemoveAddedResources, DFDeviceObjectFdoPdoRef_c1020fff-8895-4ece-ae27-ef33d3a65de6.xml, kmdf.evtdeviceremoveaddedresources
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdffdo.h
apiname:
-	EvtDeviceRemoveAddedResources
product: Windows
targetos: Windows
req.typenames: "*PWDF_DRIVER_VERSION_AVAILABLE_PARAMS, WDF_DRIVER_VERSION_AVAILABLE_PARAMS"
req.product: Windows 10 or later.
---

# EVT_WDF_DEVICE_REMOVE_ADDED_RESOURCES callback


## -description


<p class="CCE_Message">[Applies to KMDF only]

A driver's <i>EvtDeviceRemoveAddedResources</i> event callback function removes hardware resources that the driver's <a href="https://msdn.microsoft.com/7d9b38b5-989d-45a3-8771-57a8d1f98725">EvtDeviceFilterAddResourceRequirements</a> callback function added.


## -prototype


````
EVT_WDF_DEVICE_REMOVE_ADDED_RESOURCES EvtDeviceRemoveAddedResources;

NTSTATUS EvtDeviceRemoveAddedResources(
  _In_ WDFDEVICE    Device,
  _In_ WDFCMRESLIST ResourcesRaw,
  _In_ WDFCMRESLIST ResourcesTranslated
)
{ ... }
````


## -parameters




### -param Device [in]

A handle to the framework device object to which resources will be assigned.


### -param ResourcesRaw [in]

A handle to a resource list object that identifies the raw hardware resources that the PnP manager has assigned to the device. 


### -param ResourcesTranslated [in]

A handle to a resource list object that identifies the translated hardware resources that the PnP manager has assigned to the device. 


## -returns


If the driver encountered no errors it must return STATUS_SUCCESS. Otherwise it must return an NTSTATUS value that <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a> evaluates as <b>FALSE</b>.

For more information about return values, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.



## -remarks


Framework-based function drivers can provide an <i>EvtDeviceRemoveAddedResources</i> callback function. To register this callback function, drivers call <a href="..\wdffdo\nf-wdffdo-wdffdoinitseteventcallbacks.md">WdfFdoInitSetEventCallbacks</a>.

If a driver provides an <a href="https://msdn.microsoft.com/7d9b38b5-989d-45a3-8771-57a8d1f98725">EvtDeviceFilterAddResourceRequirements</a> callback function that adds resources to a device's hardware requirements list, the driver must also provide an <i>EvtDeviceRemoveAddedResources</i> callback function. The <i>EvtDeviceRemoveAddedResources</i> callback function examines the resource list that the PnP manager has assigned to the device, and removes the resources from the list that the <i>EvtDeviceFilterAddResourceRequirements</i> callback function added. If the driver removes a resource, it must remove it from both the raw and translated resource lists.

For more information about resource lists and the order in which the resources appear, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/raw-and-translated-resources">raw and translated hardware resources</a>.

The framework calls the driver's <i>EvtDeviceRemoveAddedResources</i> callback function immediately before it passes the device's resource list to the bus driver. This callback function removes added resources so that the bus driver will not attempt to use them. 

For more information about the <i>EvtDeviceRemoveAddedResources</i> callback function, see <a href="https://msdn.microsoft.com/571b2990-5627-434e-b8fc-d2564188f544">Modifying a Resource List</a>.

For more information about hardware resources, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.



## -see-also

<a href="https://msdn.microsoft.com/7d9b38b5-989d-45a3-8771-57a8d1f98725">EvtDeviceFilterAddResourceRequirements</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff540870">EvtDeviceFilterRemoveResourceRequirements</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DEVICE_REMOVE_ADDED_RESOURCES callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

