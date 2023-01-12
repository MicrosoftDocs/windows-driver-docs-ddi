---
UID: NS:wdm._DEVICE_CAPABILITIES
title: DEVICE_CAPABILITIES (wdm.h)
description: A DEVICE_CAPABILITIES structure describes PnP and power capabilities of a device. This structure is returned in response to an IRP_MN_QUERY_CAPABILITIES IRP.
tech.root: kernel
ms.date: 12/15/2022
keywords: ["DEVICE_CAPABILITIES structure"]
ms.keywords: DEVICE_CAPABILITIES, DEVICE_CAPABILITIES structure [Kernel-Mode Driver Architecture], PDEVICE_CAPABILITIES, PDEVICE_CAPABILITIES structure pointer [Kernel-Mode Driver Architecture], _DEVICE_CAPABILITIES, kernel.device_capabilities, kstruct_a_53ec6d40-84a0-45f6-a78c-73fcc3c12e11.xml, wdm/DEVICE_CAPABILITIES, wdm/PDEVICE_CAPABILITIES
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
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
req.irql: 
targetos: Windows
req.typenames: DEVICE_CAPABILITIES, PDEVICE_CAPABILITIES
f1_keywords:
 - _DEVICE_CAPABILITIES
 - wdm/_DEVICE_CAPABILITIES
 - PDEVICE_CAPABILITIES
 - wdm/PDEVICE_CAPABILITIES
 - DEVICE_CAPABILITIES
 - wdm/DEVICE_CAPABILITIES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _DEVICE_CAPABILITIES
 - PDEVICE_CAPABILITIES
 - DEVICE_CAPABILITIES
---

## -description

A **DEVICE_CAPABILITIES** structure describes PnP and power capabilities of a device. This structure is returned in response to an [IRP_MN_QUERY_CAPABILITIES](/windows-hardware/drivers/kernel/irp-mn-query-capabilities) IRP.

## -struct-fields

### -field Size

Specifies the size of the structure, in bytes. This field is set by the component that sends the **IRP_MN_QUERY_CAPABILITIES** request.

### -field Version

Specifies the version of the structure, currently version 1. This field is set by the component that sends the **IRP_MN_QUERY_CAPABILITIES** request.

### -field DeviceD1

Specifies whether the device hardware supports the D1 power state. Drivers should not change this value.

### -field DeviceD2

Specifies whether the device hardware supports the D2 power state. Drivers should not change this value.

### -field LockSupported

Specifies whether the device supports physical-device locking that prevents device ejection. This member pertains to ejecting the device from its slot, rather than ejecting a piece of removable media from the device.

### -field EjectSupported

Specifies whether the device supports software-controlled device ejection while the system is in the **PowerSystemWorking** state. This member pertains to ejecting the device from its slot, rather than ejecting a piece of removable media from the device.

### -field Removable

Specifies whether the device can be dynamically removed from its immediate parent. If **Removable** is set to **TRUE**, the device does not belong to the same physical object as its parent.

For example, if **Removable** is set to **TRUE** for a USB composite device inside a multifunction printer, the composite device does not belong to the physical object of its immediate parent, such as a USB hub inside a notebook PC.

In most cases the bus driver, not the function driver, should determine the value of the **Removable** parameter of the device. For USB devices, the USB hub driver sets the **Removable** parameter. It should not be modified by the function driver.

If **Removable** is set to **TRUE**, the device is displayed in the **Unplug or Eject Hardware** program, unless **SurpriseRemovalOK** is also set to **TRUE**.

### -field DockDevice

Specifies whether the device is a docking peripheral.

### -field UniqueID

Specifies whether the device's instance ID is unique system-wide. This bit is clear if the instance ID is unique only within the scope of the bus. For more information, see [Device Identification Strings](/windows-hardware/drivers/install/device-identification-strings).

### -field SilentInstall

Specifies whether Device Manager should suppress all installation dialog boxes; except required dialog boxes such as "no compatible drivers found."

### -field RawDeviceOK

Specifies whether the driver for the underlying bus can drive the device if there is no function driver (for example, SCSI devices in pass-through mode). This mode of operation is called [raw mode](/windows-hardware/drivers/).

### -field SurpriseRemovalOK

Specifies whether the function driver for the device can handle the case where the device is removed before Windows can send **IRP_MN_QUERY_REMOVE_DEVICE** to it. If **SurpriseRemovalOK** is set to **TRUE**, the device can be safely removed from its immediate parent regardless of the state that its driver is in.

For example, a standard USB mouse does not maintain any state in its hardware and thus can be safely removed at any time. However, an external hard disk whose driver caches writes in memory cannot be safely removed without first letting the driver flush its cache to the hardware.

Drivers for USB devices that support surprise removal must set this to **TRUE** only when the IRP is being passed back up the driver stack.

### -field WakeFromD0

Specifies whether the device can respond to an external wake signal while in the D0 state. Drivers should not change this value.

### -field WakeFromD1

Specifies whether the device can respond to an external wake signal while in the D1 state. Drivers should not change this value.

### -field WakeFromD2

Specifies whether the device can respond to an external wake signal while in the D2 state. Drivers should not change this value.

### -field WakeFromD3

Specifies whether the device can respond to an external wake signal while in the D3 state. Drivers should not change this value.

### -field HardwareDisabled

When set, this flag specifies that the device's hardware is disabled.

A device's parent bus driver or a bus filter driver sets this flag when such a driver determines that the device hardware is disabled.

The PnP manager sends one **IRP_MN_QUERY_CAPABILITIES** IRP right after a device is enumerated and sends another after the device has been started. The PnP manager only checks this bit right after the device is enumerated. Once the device is started, this bit is ignored.

### -field NonDynamic

Reserved for future use.

### -field WarmEjectSupported

Reserved for future use.

### -field NoDisplayInUI

Do not display the device in the user interface. If this bit is set, the device is never displayed in the user interface, even if the device is present but fails to start. Only bus drivers and associated bus filter drivers should set this bit. (Also see the **PNP_DEVICE_DONT_DISPLAY_IN_UI** flag in the [PNP_DEVICE_STATE](/windows-hardware/drivers/kernel/handling-an-irp-mn-surprise-removal-request#about-pnp_device_state) structure.)

### -field Reserved1

Reserved for system use.

### -field WakeFromInterrupt

Indicates whether the driver or ACPI is responsible for handling the wake event. If set, the driver is responsible for handling the wake event. ACPI arms the device when it receives an IRP_MN_WAIT_WAKE IRP, but does not connect the interrupt, complete the IRP to notify the device stack of a wake event.

### -field SecureDevice

Indicates whether the device is a secure device.

### -field ChildOfVgaEnabledBridge

For a VGA device, indicates whether the parent bridge has the VGA decoding bit set.

### -field DecodeIoOnBoot

Indictates whether the device has IO decode enabled on boot.

### -field Reserved

Reserved for system use.

### -field Address

Specifies an address indicating where the device is located on its underlying bus.

The interpretation of this number is bus-specific. If the address is unknown or the bus driver does not support an address, the bus driver leaves this member at its default value of 0xFFFFFFFF.

The following list describes the information certain bus drivers store in the **Address** field for their child devices:

| Bus | Description |
|---|---|
| 1394 | Does not supply an address because the addresses are volatile. Defaults to 0xFFFFFFFF. |
| EISA | Slot Number (0-F). |
| IDE | For an IDE device, the address contains the target ID and LUN. For an IDE channel, the address is zero or one (0 = primary channel and 1 = secondary channel). |
| ISApnp | Does not supply an address. Defaults to 0xFFFFFFFF. |
| PC Card (PCMCIA) | The socket number (typically 0x00 or 0x40). |
| PCI | The device number in the high word and the function number in the low word. |
| SCSI | The target ID. |
| USB | The port number. |

### -field UINumber

Specifies a number associated with the device that can be displayed in the user interface.

This number is typically a user-perceived slot number, such as a number printed next to the slot on the board, or some other number that makes locating the physical device easier for the user. For buses with no such convention, or when the **UINumber** is unknown, the bus driver leaves this member at its default value of 0xFFFFFFFF.

### -field DeviceState

An array of values indicating the most-powered device power state that the device can maintain for each system power state. The **DeviceState[PowerSystemWorking]** element of the array corresponds to the S0 system state. The entry for **PowerSystemUnspecified** is reserved for system use.

The entries in this array are based on the capabilities of the parent devnode. As a general rule, a driver should not change these values. However, if necessary, a driver can lower the value, for example, from **PowerDeviceD1** to **PowerDeviceD2**.

If the bus driver is unable to determine the appropriate device power state for a root-enumerated device, it sets **DeviceState[PowerSystemWorking]** to **PowerDeviceD0** and all other entries to **PowerDeviceD3**.

### -field SystemWake

Specifies the least-powered system power state from which the device can signal a wake event. A value of **PowerSystemUnspecified** indicates that the device cannot wake the system.

A bus driver can get this information from its parent devnode.

In general, a driver should not change this value. If necessary, however, a driver can raise the power state, for example, from **PowerSystemHibernate** to **PowerSystemS1**, to indicate that its device cannot wake the system from a hibernation state but can from a higher-powered sleep state.

### -field DeviceWake

Specifies the least-powered device power state from which the device can signal a wake event. A value of **PowerDeviceUnspecified** indicates that the device cannot signal a wake event.

### -field D1Latency

Specifies the device's approximate worst-case latency, in 100-microsecond units, for returning the device to the **PowerDeviceD0** state from the **PowerDeviceD1** state. Set to zero if the device does not support the D1 state.

### -field D2Latency

Specifies the device's approximate worst-case latency, in 100-microsecond units, for returning the device to the **PowerDeviceD0** state from the **PowerDeviceD2** state. Set to zero if the device does not support the D2 state.

### -field D3Latency

Specifies the device's approximate worst-case latency, in 100-microsecond units, for returning the device to the **PowerDeviceD0** state from the **PowerDeviceD3** state. Set to zero if the device does not support the D3 state.

## -remarks

Bus drivers set the appropriate values in this structure in response to an **IRP_MN_QUERY_CAPABILITIES** IRP. Bus filter drivers, function drivers, and filter drivers might alter the capabilities set by the bus driver.

Drivers that send an **IRP_MN_QUERY_CAPABILITIES** request must initialize the **Size**, **Version**, **Address**, and **UINumber** members of this structure before sending the IRP.

For more information about using the **DEVICE_CAPABILITIES** structure to describe a device's power capabilities, see [Reporting Device Power Capabilities](/windows-hardware/drivers/kernel/reporting-device-power-capabilities).

## -see-also

[IRP_MN_QUERY_CAPABILITIES](/windows-hardware/drivers/kernel/irp-mn-query-capabilities)

[PNP_DEVICE_STATE](/windows-hardware/drivers/kernel/handling-an-irp-mn-surprise-removal-request#about-pnp_device_state)
