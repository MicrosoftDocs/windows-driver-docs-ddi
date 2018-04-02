---
UID: NF:wdffdo.WdfFdoInitSetEventCallbacks
title: WdfFdoInitSetEventCallbacks function
author: windows-driver-content
description: The WdfFdoInitSetEventCallbacks method registers a framework-based function driver's event callback functions, for a specified device.
old-location: wdf\wdffdoinitseteventcallbacks.htm
old-project: wdf
ms.assetid: 0a47ea47-590c-4395-b38e-d1f1fb1929e1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_3a3fbec9-836c-422e-a921-654fa4866989.xml, WdfFdoInitSetEventCallbacks, WdfFdoInitSetEventCallbacks method, kmdf.wdffdoinitseteventcallbacks, wdf.wdffdoinitseteventcallbacks, wdffdo/WdfFdoInitSetEventCallbacks
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfFdoInitSetEventCallbacks
product:
- Windows
targetos: Windows
req.typenames: WDF_DRIVER_VERSION_AVAILABLE_PARAMS, *PWDF_DRIVER_VERSION_AVAILABLE_PARAMS
req.product: Windows 10 or later.
---

# WdfFdoInitSetEventCallbacks function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfFdoInitSetEventCallbacks</b> method registers a framework-based function driver's event callback functions, for a specified device.


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure that the driver obtained from its <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function.


### -param FdoEventCallbacks [in]

A pointer to a driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff551311">WDF_FDO_EVENT_CALLBACKS</a> structure.


## -returns



None




## -remarks



Before calling <b>WdfFdoInitSetEventCallbacks</b>, the driver must allocate a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551311">WDF_FDO_EVENT_CALLBACKS</a> structure and fill in the structure with pointers to the driver's event callback functions.

The driver must call <b>WdfFdoInitSetEventCallbacks</b> before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551313">WDF_FDO_EVENT_CALLBACKS_INIT</a>
 

 

