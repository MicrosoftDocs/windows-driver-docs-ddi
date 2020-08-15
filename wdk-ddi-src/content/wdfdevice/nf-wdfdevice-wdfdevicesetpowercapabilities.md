---
UID: NF:wdfdevice.WdfDeviceSetPowerCapabilities
title: WdfDeviceSetPowerCapabilities function (wdfdevice.h)
description: The WdfDeviceSetPowerCapabilities method reports a device's power capabilities.
old-location: wdf\wdfdevicesetpowercapabilities.htm
tech.root: wdf
ms.assetid: e04558e3-a95a-408b-961b-e8ea7ac9136d
ms.date: 02/26/2018
keywords: ["WdfDeviceSetPowerCapabilities function"]
ms.keywords: DFDeviceObjectGeneralRef_d3d51bfe-62da-4146-b4c1-152cac9f0e82.xml, WdfDeviceSetPowerCapabilities, WdfDeviceSetPowerCapabilities method, kmdf.wdfdevicesetpowercapabilities, wdf.wdfdevicesetpowercapabilities, wdfdevice/WdfDeviceSetPowerCapabilities
f1_keywords:
 - "wdfdevice/WdfDeviceSetPowerCapabilities"
 - "WdfDeviceSetPowerCapabilities"
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfDeviceSetPowerCapabilities
targetos: Windows
req.typenames: 
---

# WdfDeviceSetPowerCapabilities function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDeviceSetPowerCapabilities</b> method reports a device's power capabilities.


## -parameters




### -param Device 
[in]
A handle to a framework device object.


### -param PowerCapabilities 
[in]
A pointer to a driver-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_capabilities">WDF_DEVICE_POWER_CAPABILITIES</a> structure.


## -remarks

A bug check occurs if the driver supplies an invalid object handle.




A driver typically calls <b>WdfDeviceSetPowerCapabilities</b> from within one of the following callback functions:

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_entry">EvtDeviceD0Entry</a> (if the <i>PreviousState</i> parameter's value is <b>WdfPowerDeviceD3Final</b>) 

</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_init">EvtDeviceSelfManagedIoInit</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_create_device">EvtChildListCreateDevice</a>


</li>
</ul>
If more than one driver in the device's driver stack call <b>WdfDeviceSetPowerCapabilities</b>, the power manager uses the values that are supplied by the driver that is highest in the stack.


#### Examples

The following code example initializes a WDF_DEVICE_POWER_CAPABILITIES structure and then calls <b>WdfDeviceSetPowerCapabilities</b>.

```cpp
WDF_DEVICE_POWER_CAPABILITIES powerCaps;

WDF_DEVICE_POWER_CAPABILITIES_INIT(&powerCaps);
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
                              &powerCaps
                              );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_capabilities">WDF_DEVICE_POWER_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdf_device_power_capabilities_init">WDF_DEVICE_POWER_CAPABILITIES_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicesetpnpcapabilities">WdfDeviceSetPnpCapabilities</a>
 

 

