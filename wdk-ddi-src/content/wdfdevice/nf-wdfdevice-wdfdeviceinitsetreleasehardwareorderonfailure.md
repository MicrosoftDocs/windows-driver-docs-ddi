---
UID: NF:wdfdevice.WdfDeviceInitSetReleaseHardwareOrderOnFailure
title: WdfDeviceInitSetReleaseHardwareOrderOnFailure function (wdfdevice.h)
description: The WdfDeviceInitSetReleaseHardwareOrderOnFailure method specifies whether the framework calls the driver's EvtDeviceReleaseHardware callback function immediately after device failure, or waits until all child devices have been removed.
old-location: wdf\wdfdeviceinitsetreleasehardwareorderonfailure.htm
tech.root: wdf
ms.assetid: 5DC3C7C8-E7D1-4874-AF8D-8E6FD48DF046
ms.date: 02/26/2018
keywords: ["WdfDeviceInitSetReleaseHardwareOrderOnFailure function"]
ms.keywords: WdfDeviceInitSetReleaseHardwareOrderOnFailure, WdfDeviceInitSetReleaseHardwareOrderOnFailure method, kmdf.wdfdeviceinitsetreleasehardwareorderonfailure, wdf.wdfdeviceinitsetreleasehardwareorderonfailure, wdfdevice/WdfDeviceInitSetReleaseHardwareOrderOnFailure
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfDeviceInitSetReleaseHardwareOrderOnFailure
 - wdfdevice/WdfDeviceInitSetReleaseHardwareOrderOnFailure
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
 - WdfDeviceInitSetReleaseHardwareOrderOnFailure
---

# WdfDeviceInitSetReleaseHardwareOrderOnFailure function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>


   The <b>WdfDeviceInitSetReleaseHardwareOrderOnFailure</b> method specifies whether the framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_release_hardware">EvtDeviceReleaseHardware</a> callback function immediately after device failure, or waits until all child devices have been removed.

## -parameters

### -param DeviceInit 

[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure.

### -param ReleaseHardwareOrderOnFailure 

[in]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_release_hardware_order_on_failure">WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE</a>-typed enumerator that specifies when the framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_release_hardware">EvtDeviceReleaseHardware</a> callback function.

## -remarks

Typically, the framework calls a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_release_hardware">EvtDeviceReleaseHardware</a> callback function after it has called the <i>EvtDeviceReleaseHardware</i> function for all child devices that the driver enumerates.

In the event of a device power-up or power-down failure, however, the framework might call the  driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_release_hardware">EvtDeviceReleaseHardware</a> before it has called the <i>EvtDeviceReleaseHardware</i> functions for all child devices.

To override this default behavior, a driver can call <b>WdfDeviceInitSetReleaseHardwareOrderOnFailure</b> to specify that, even in device failure scenarios, the framework should always wait to call its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_release_hardware">EvtDeviceReleaseHardware</a> function until it has called the <i>EvtDeviceReleaseHardware</i> functions of the child devices.

 For example, a bus driver that performs hardware access on behalf of its child devices could use this technique to ensure that its child devices do not request access to hardware after the framework has called the bus driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_release_hardware">EvtDeviceReleaseHardware</a> callback function.

If a driver calls <b>WdfDeviceInitSetReleaseHardwareOrderOnFailure</b>, it must do so before it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.


#### Examples

The following code example shows how a bus driver can request that the framework wait to call its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_release_hardware">EvtDeviceReleaseHardware</a> callback function until all of its child devices have been removed.

```cpp
WdfDeviceInitSetReleaseHardwareOrderOnFailure(
                       DeviceInit,
                       WdfReleaseHardwareOrderOnFailureAfterDescendants
                       );
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_release_hardware">EvtDeviceReleaseHardware</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_release_hardware_order_on_failure">WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE</a>

