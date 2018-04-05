---
UID: NF:wdfdevice.WdfDeviceSetPowerCapabilities
title: WdfDeviceSetPowerCapabilities function
author: windows-driver-content
description: The WdfDeviceSetPowerCapabilities method reports a device's power capabilities.
old-location: wdf\wdfdevicesetpowercapabilities.htm
old-project: wdf
ms.assetid: e04558e3-a95a-408b-961b-e8ea7ac9136d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_d3d51bfe-62da-4146-b4c1-152cac9f0e82.xml, WdfDeviceSetPowerCapabilities, WdfDeviceSetPowerCapabilities method, kmdf.wdfdevicesetpowercapabilities, wdf.wdfdevicesetpowercapabilities, wdfdevice/WdfDeviceSetPowerCapabilities
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfDeviceSetPowerCapabilities
product:
- Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceSetPowerCapabilities function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceSetPowerCapabilities</b> method reports a device's power capabilities.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param PowerCapabilities [in]

A pointer to a driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff551264">WDF_DEVICE_POWER_CAPABILITIES</a> structure.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



A driver typically calls <b>WdfDeviceSetPowerCapabilities</b> from within one of the following callback functions:

<ul>
<li>

<a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a>


</li>
<li>

<a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a>


</li>
<li>

<a href="https://msdn.microsoft.com/0cfabb0f-2d5e-4445-8683-d2916de5b549">EvtDeviceD0Entry</a> (if the <i>PreviousState</i> parameter's value is <b>WdfPowerDeviceD3Final</b>) 

</li>
<li>

<a href="https://msdn.microsoft.com/9dbc66db-ea94-4e6a-9618-00999a9dd641">EvtDeviceSelfManagedIoInit</a>


</li>
<li>

<a href="https://msdn.microsoft.com/296fbe06-1680-43a8-b5c3-1a1faa19c6c3">EvtChildListCreateDevice</a>


</li>
</ul>
If more than one driver in the device's driver stack call <b>WdfDeviceSetPowerCapabilities</b>, the power manager uses the values that are supplied by the driver that is highest in the stack.


#### Examples

The following code example initializes a WDF_DEVICE_POWER_CAPABILITIES structure and then calls <b>WdfDeviceSetPowerCapabilities</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_DEVICE_POWER_CAPABILITIES powerCaps;

WDF_DEVICE_POWER_CAPABILITIES_INIT(&amp;powerCaps);
powerCaps.DeviceD1 = WdfTrue;
powerCaps.WakeFromD1 = WdfTrue;
powerCaps.DeviceWake = PowerDeviceD1;
powerCaps.DeviceState[PowerSystemWorking] = PowerDeviceD1;
powerCaps.DeviceState[PowerSystemSleeping1] = PowerDeviceD1;
powerCaps.DeviceState[PowerSystemSleeping2] = PowerDeviceD2;
powerCaps.DeviceState[PowerSystemSleeping3] = PowerDeviceD2;
powerCaps.DeviceState[PowerSystemHibernate] = PowerDeviceD3;
powerCaps.DeviceState[PowerSystemShutdown] = PowerDeviceD3;

WdfDeviceSetPowerCapabilities(
                              device,
                              &amp;powerCaps
                              );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551264">WDF_DEVICE_POWER_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551265">WDF_DEVICE_POWER_CAPABILITIES_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546898">WdfDeviceSetPnpCapabilities</a>
 

 

