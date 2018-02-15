---
UID: NF:wdffdo.WdfFdoInitSetEventCallbacks
title: WdfFdoInitSetEventCallbacks function
author: windows-driver-content
description: The WdfFdoInitSetEventCallbacks method registers a framework-based function driver's event callback functions, for a specified device.
old-location: wdf\wdffdoinitseteventcallbacks.htm
old-project: wdf
ms.assetid: 0a47ea47-590c-4395-b38e-d1f1fb1929e1
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdffdo/WdfFdoInitSetEventCallbacks, PFN_WDFFDOINITSETEVENTCALLBACKS, DFDeviceObjectFdoPdoRef_3a3fbec9-836c-422e-a921-654fa4866989.xml, kmdf.wdffdoinitseteventcallbacks, WdfFdoInitSetEventCallbacks method, wdf.wdffdoinitseteventcallbacks, WdfFdoInitSetEventCallbacks
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdffdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfFdoInitSetEventCallbacks
product: Windows
targetos: Windows
req.typenames: "*PWDF_DRIVER_VERSION_AVAILABLE_PARAMS, WDF_DRIVER_VERSION_AVAILABLE_PARAMS"
req.product: Windows 10 or later.
---

# WdfFdoInitSetEventCallbacks function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfFdoInitSetEventCallbacks</b> method registers a framework-based function driver's event callback functions, for a specified device.


## -syntax


````
VOID WdfFdoInitSetEventCallbacks(
  _In_ PWDFDEVICE_INIT          DeviceInit,
  _In_ PWDF_FDO_EVENT_CALLBACKS FdoEventCallbacks
);
````


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure that the driver obtained from its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function.


### -param FdoEventCallbacks [in]

A pointer to a driver-allocated <a href="..\wdffdo\ns-wdffdo-_wdf_fdo_event_callbacks.md">WDF_FDO_EVENT_CALLBACKS</a> structure.


## -returns



None




## -remarks



Before calling <b>WdfFdoInitSetEventCallbacks</b>, the driver must allocate a <a href="..\wdffdo\ns-wdffdo-_wdf_fdo_event_callbacks.md">WDF_FDO_EVENT_CALLBACKS</a> structure and fill in the structure with pointers to the driver's event callback functions.

The driver must call <b>WdfFdoInitSetEventCallbacks</b> before calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

For more information about the <b>WdfFdoInitSetEventCallbacks</b> method, see <a href="https://msdn.microsoft.com/3b988f6d-c50e-412d-85cb-031746535ff4">Creating Device Objects in a Function Driver</a>.


#### Examples

The following code example initializes a WDF_FDO_EVENT_CALLBACKS structure and then calls <b>WdfFdoInitSetEventCallbacks</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_FDO_EVENT_CALLBACKS fdoCallbacks;

WDF_FDO_EVENT_CALLBACKS_INIT(&amp;fdoCallbacks);
fdoCallbacks.EvtDeviceFilterAddResourceRequirements = MyEvtDeviceFilterAddResourceRequirements;
fdoCallbacks.EvtDeviceFilterRemoveResourceRequirements = MyEvtDeviceFilterRemoveResourceRequirements;
fdoCallbacks.EvtDeviceRemoveAddedResources = MyEvtDeviceRemoveAddedResources;

WdfFdoInitSetEventCallbacks(
                            DeviceInit,
                            &amp;fdoCallbacks
                            );</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdffdo\nf-wdffdo-wdf_fdo_event_callbacks_init.md">WDF_FDO_EVENT_CALLBACKS_INIT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfFdoInitSetEventCallbacks method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

