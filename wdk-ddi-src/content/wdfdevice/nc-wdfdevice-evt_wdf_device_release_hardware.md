---
UID: NC:wdfdevice.EVT_WDF_DEVICE_RELEASE_HARDWARE
title: EVT_WDF_DEVICE_RELEASE_HARDWARE (wdfdevice.h)
description: A driver's EvtDeviceReleaseHardware event callback function performs operations that are needed when a device is no longer accessible.
old-location: wdf\evtdevicereleasehardware.htm
tech.root: wdf
ms.assetid: b4c17e57-688c-4c76-892c-5c8abbf83f20
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_RELEASE_HARDWARE callback function"]
ms.keywords: DFDeviceObjectGeneralRef_aaaf477b-f2be-4b26-a607-cb057d976dc1.xml, EVT_WDF_DEVICE_RELEASE_HARDWARE, EVT_WDF_DEVICE_RELEASE_HARDWARE callback, EvtDeviceReleaseHardware, EvtDeviceReleaseHardware callback function, kmdf.evtdevicereleasehardware, wdf.evtdevicereleasehardware, wdfdevice/EvtDeviceReleaseHardware
f1_keywords:
 - "wdfdevice/EvtDeviceReleaseHardware"
 - "EvtDeviceReleaseHardware"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
- Wdfdevice.h
api_name:
- EvtDeviceReleaseHardware
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_RELEASE_HARDWARE callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceReleaseHardware</i> event callback function performs operations that are needed when a device is no longer accessible.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param ResourcesTranslated [in]

A handle to a resource list object that identifies the translated hardware resources that the Plug and Play manager has assigned to the device.


## -returns



If the <i>EvtDeviceReleaseHardware</i> callback function encounters no errors, it must return STATUS_SUCCESS or another status value for which <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise, it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. Do not return STATUS_NOT_SUPPORTED.




## -remarks



To register an <i>EvtDeviceReleaseHardware</i> callback function, your driver must call  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

If a driver has registered an <i>EvtDeviceReleaseHardware</i> callback function, the framework calls it during the following transitions: <ul>
<li>Resource rebalancing</li>
<li>Orderly removal</li>
<li>Surprise removal</li>
</ul>


The framework calls the <i>EvtDeviceReleaseHardware</i> callback function after the framework has stopped sending I/O requests to the device, any interrupts assigned to the device have been disabled and disconnected, and the device has been turned off.  

 When the framework calls the <i>EvtDeviceReleaseHardware</i>, the PDO for the device still exists and can be queried for device information that is available in the powered off state, for example PCI configuration state.

In addition, the translated hardware resources that the framework supplies to <i>EvtDeviceReleaseHardware</i> are still assigned to the device.  The primary purpose of this callback function is to release those resources, and in particular to unmap any memory resources that the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a> callback function mapped.  The driver can also use this callback to perform any other driver or device management activity that might be required in the powered down state. Usually, all other hardware shutdown operations should take place in the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_exit">EvtDeviceD0Exit</a> callback function.

The framework always calls the driver's <i>EvtDeviceReleaseHardware</i> callback function if the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a> callback function has been called, even if <i>EvtDevicePrepareHardware</i> returned a failure code.

A driver for a device that has child devices can control the order in which the framework calls the <i>EvtDeviceReleaseHardware</i> callback functions for the parent device and its children by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetreleasehardwareorderonfailure">WdfDeviceInitSetReleaseHardwareOrderOnFailure</a> from within its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function.

For more information about when the framework calls this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/pnp-and-power-management-scenarios">PnP and Power Management Scenarios</a>.

For more information about hardware resources, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.

For more information about drivers that provide this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-pnp-and-power-management-in-function-drivers">Supporting PnP and Power Management in Function Drivers</a>.





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a>
 

 

