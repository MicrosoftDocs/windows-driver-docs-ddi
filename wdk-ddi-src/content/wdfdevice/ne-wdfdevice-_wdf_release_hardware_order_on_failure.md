---
UID: NE:wdfdevice._WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE
title: _WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE (wdfdevice.h)
description: The WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE enumeration specifies when the framework calls a driver's EvtDeviceReleaseHardware callback function.
old-location: wdf\wdf_release_hardware_order_on_failure.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE enumeration"]
ms.keywords: "*PWDF_RELEASE_HARDWARE_ORDER_ON_FAILURE, PWDF_RELEASE_HARDWARE_ORDER_ON_FAILURE, PWDF_RELEASE_HARDWARE_ORDER_ON_FAILURE enumeration pointer, WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE, WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE enumeration, WdfReleaseHardwareOrderOnFailureAfterDescendants, WdfReleaseHardwareOrderOnFailureEarly, WdfReleaseHardwareOrderOnFailureInvalid, _WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE, kmdf.wdf_release_hardware_order_on_failure, wdf.wdf_release_hardware_order_on_failure, wdfdevice/PWDF_RELEASE_HARDWARE_ORDER_ON_FAILURE, wdfdevice/WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE, wdfdevice/WdfReleaseHardwareOrderOnFailureAfterDescendants, wdfdevice/WdfReleaseHardwareOrderOnFailureEarly, wdfdevice/WdfReleaseHardwareOrderOnFailureInvalid"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
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
req.irql: 
targetos: Windows
req.typenames: WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE, *PWDF_RELEASE_HARDWARE_ORDER_ON_FAILURE
f1_keywords:
 - _WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE
 - wdfdevice/_WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE
 - PWDF_RELEASE_HARDWARE_ORDER_ON_FAILURE
 - wdfdevice/PWDF_RELEASE_HARDWARE_ORDER_ON_FAILURE
 - WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE
 - wdfdevice/WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfdevice.h
api_name:
 - _WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE
 - PWDF_RELEASE_HARDWARE_ORDER_ON_FAILURE
 - WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE
---

# _WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE enumeration


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>


   The <b>WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE</b> enumeration specifies when the framework calls a driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_release_hardware">EvtDeviceReleaseHardware</a> callback function.

## -enum-fields

### -field WdfReleaseHardwareOrderOnFailureInvalid:0

Reserved for system use.

### -field WdfReleaseHardwareOrderOnFailureEarly

Except under certain error conditions, the framework calls the driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_release_hardware">EvtDeviceReleaseHardware</a> callback function after it has called the <i>EvtDeviceReleaseHardware</i> function for all child devices that the driver enumerates. For more information, see Remarks.

### -field WdfReleaseHardwareOrderOnFailureAfterDescendants

The framework always calls the driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_release_hardware">EvtDeviceReleaseHardware</a> callback function after it has called the <i>EvtDeviceReleaseHardware</i> function for all child devices that the driver enumerates.

## -remarks

The <b>WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE</b> enumeration is used as input to  <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetreleasehardwareorderonfailure">WdfDeviceInitSetReleaseHardwareOrderOnFailure</a>.

If a driver specifies <b>WdfReleaseHardwareOrderOnFailureEarly</b>, then in normal device removal, the framework calls the driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_release_hardware">EvtDeviceReleaseHardware</a> after it has called the <i>EvtDeviceReleaseHardware</i> function for all child devices that the driver enumerates. However, in the event of a device power-up or power-down failure, the framework might call the  driver's <i>EvtDeviceReleaseHardware</i> before it has called the <i>EvtDeviceReleaseHardware</i> functions for all child devices.

If a driver specifies <b>WdfReleaseHardwareOrderOnFailureAfterDescendants</b>, then the framework waits to  call the driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_release_hardware">EvtDeviceReleaseHardware</a> until it has called the <i>EvtDeviceReleaseHardware</i> functions of the child devices.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_release_hardware">EvtDeviceReleaseHardware</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetreleasehardwareorderonfailure">WdfDeviceInitSetReleaseHardwareOrderOnFailure</a>

