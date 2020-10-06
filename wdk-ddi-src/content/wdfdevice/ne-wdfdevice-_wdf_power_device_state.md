---
UID: NE:wdfdevice._WDF_POWER_DEVICE_STATE
title: _WDF_POWER_DEVICE_STATE (wdfdevice.h)
description: The WDF_POWER_DEVICE_STATE enumeration identifies the device power states that a device might support.
old-location: wdf\wdf_power_device_state.htm
tech.root: wdf
ms.assetid: 66ff00fd-43b0-4fe1-a010-4b5ef65fa811
ms.date: 02/26/2018
keywords: ["WDF_POWER_DEVICE_STATE enumeration"]
ms.keywords: "*PWDF_POWER_DEVICE_STATE, DFDeviceObjectGeneralRef_5a921767-81e1-4a80-b775-8f91819c6ea5.xml, PWDF_POWER_DEVICE_STATE, PWDF_POWER_DEVICE_STATE enumeration pointer, WDF_POWER_DEVICE_STATE, WDF_POWER_DEVICE_STATE enumeration, WdfPowerDeviceD0, WdfPowerDeviceD1, WdfPowerDeviceD2, WdfPowerDeviceD3, WdfPowerDeviceD3Final, WdfPowerDeviceInvalid, WdfPowerDeviceMaximum, WdfPowerDevicePrepareForHibernation, _WDF_POWER_DEVICE_STATE, kmdf.wdf_power_device_state, wdf.wdf_power_device_state, wdfdevice/PWDF_POWER_DEVICE_STATE, wdfdevice/WDF_POWER_DEVICE_STATE, wdfdevice/WdfPowerDeviceD0, wdfdevice/WdfPowerDeviceD1, wdfdevice/WdfPowerDeviceD2, wdfdevice/WdfPowerDeviceD3, wdfdevice/WdfPowerDeviceD3Final, wdfdevice/WdfPowerDeviceInvalid, wdfdevice/WdfPowerDeviceMaximum, wdfdevice/WdfPowerDevicePrepareForHibernation"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
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
req.irql: 
targetos: Windows
req.typenames: WDF_POWER_DEVICE_STATE, *PWDF_POWER_DEVICE_STATE
f1_keywords:
 - _WDF_POWER_DEVICE_STATE
 - wdfdevice/_WDF_POWER_DEVICE_STATE
 - PWDF_POWER_DEVICE_STATE
 - wdfdevice/PWDF_POWER_DEVICE_STATE
 - WDF_POWER_DEVICE_STATE
 - wdfdevice/WDF_POWER_DEVICE_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfdevice.h
api_name:
 - WDF_POWER_DEVICE_STATE
---

# _WDF_POWER_DEVICE_STATE enumeration (wdfdevice.h)


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_POWER_DEVICE_STATE</b> enumeration identifies the <a href="/windows-hardware/drivers/kernel/device-power-states">device power states</a> that a device might support.

## -enum-fields

### -field WdfPowerDeviceInvalid

The device power state is invalid or unknown.

### -field WdfPowerDeviceD0

The D0 device power state.

### -field WdfPowerDeviceD1

The D1 device power state.

### -field WdfPowerDeviceD2

The D2 device power state.

### -field WdfPowerDeviceD3

The D3 device power state.

### -field WdfPowerDeviceD3Final

Represents the final time that the device enters the D3 device power state. Typically, this enumerator means that the system is being turned off, the device is about to be removed, or a <a href="/windows-hardware/drivers/wdf/the-pnp-manager-redistributes-system-resources">resource rebalance</a> is in progress. The device might have been already removed.

### -field WdfPowerDevicePrepareForHibernation

The device supports hibernation files, and the system is ready to hibernate by entering <a href="/windows-hardware/drivers/kernel/system-sleeping-states">system state S4</a>. The driver must not turn off the device. For more information, see <a href="/windows-hardware/drivers/wdf/supporting-special-files">Supporting Special Files</a>.

### -field WdfPowerDeviceMaximum

The maximum enumerator value for this enumeration.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_entry">EvtDeviceD0Entry</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_exit">EvtDeviceD0Exit</a>