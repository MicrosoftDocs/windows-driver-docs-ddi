---
UID: NS:wdm._DEVICE_CAPABILITIES
title: "_DEVICE_CAPABILITIES"
author: windows-driver-content
description: A DEVICE_CAPABILITIES structure describes PnP and power capabilities of a device. This structure is returned in response to an IRP_MN_QUERY_CAPABILITIES IRP.
old-location: kernel\device_capabilities.htm
old-project: kernel
ms.assetid: 1edae050-8e72-42e7-9dc9-8f449699969c
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/PDEVICE_CAPABILITIES, PDEVICE_CAPABILITIES structure pointer [Kernel-Mode Driver Architecture], kstruct_a_53ec6d40-84a0-45f6-a78c-73fcc3c12e11.xml, _DEVICE_CAPABILITIES, wdm/DEVICE_CAPABILITIES, kernel.device_capabilities, PDEVICE_CAPABILITIES, DEVICE_CAPABILITIES structure [Kernel-Mode Driver Architecture], DEVICE_CAPABILITIES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	DEVICE_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: DEVICE_CAPABILITIES, PDEVICE_CAPABILITIES
req.product: Windows 10 or later.
---

# _DEVICE_CAPABILITIES structure


## -description


A <b>DEVICE_CAPABILITIES</b> structure describes PnP and power capabilities of a device. This structure is returned in response to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551664">IRP_MN_QUERY_CAPABILITIES</a> IRP.


## -syntax


````
typedef struct _DEVICE_CAPABILITIES {
  USHORT             Size;
  USHORT             Version;
  ULONG              DeviceD1  :1;
  ULONG              DeviceD2  :1;
  ULONG              LockSupported  :1;
  ULONG              EjectSupported  :1;
  ULONG              Removable  :1;
  ULONG              DockDevice  :1;
  ULONG              UniqueID  :1;
  ULONG              SilentInstall  :1;
  ULONG              RawDeviceOK  :1;
  ULONG              SurpriseRemovalOK  :1;
  ULONG              WakeFromD0  :1;
  ULONG              WakeFromD1  :1;
  ULONG              WakeFromD2  :1;
  ULONG              WakeFromD3  :1;
  ULONG              HardwareDisabled  :1;
  ULONG              NonDynamic  :1;
  ULONG              WarmEjectSupported  :1;
  ULONG              NoDisplayInUI  :1;
  ULONG              Reserved1  :1;
  ULONG              Reserved  :13;
  ULONG              Address;
  ULONG              UINumber;
  DEVICE_POWER_STATE DeviceState[POWER_SYSTEM_MAXIMUM];
  SYSTEM_POWER_STATE SystemWake;
  DEVICE_POWER_STATE DeviceWake;
  ULONG              D1Latency;
  ULONG              D2Latency;
  ULONG              D3Latency;
} DEVICE_CAPABILITIES, *PDEVICE_CAPABILITIES;
````


## -struct-fields




### -field Size

Specifies the size of the structure, in bytes. This field is set by the component that sends the <b>IRP_MN_QUERY_CAPABILITIES</b> request.


### -field Version

Specifies the version of the structure, currently version 1. This field is set by the component that sends the <b>IRP_MN_QUERY_CAPABILITIES</b> request.


### -field DeviceD1

Specifies whether the device hardware supports the D1 power state. Drivers should not change this value.


### -field DeviceD2

Specifies whether the device hardware supports the D2 power state. Drivers should not change this value.


### -field LockSupported

Specifies whether the device supports physical-device locking that prevents device ejection. This member pertains to ejecting the device from its slot, rather than ejecting a piece of removable media from the device.


### -field EjectSupported

Specifies whether the device supports software-controlled device ejection while the system is in the <b>PowerSystemWorking</b> state. This member pertains to ejecting the device from its slot, rather than ejecting a piece of removable media from the device.


### -field Removable

Specifies whether the device can be dynamically removed from its immediate parent. If <b>Removable</b> is set to <b>TRUE</b>, the device does not belong to the same physical object as its parent.

For example, if <b>Removable</b> is set to <b>TRUE</b> for a USB composite device inside a multifunction printer, the composite device does not belong to the physical object of its immediate parent, such as a USB hub inside a notebook PC. 

In most cases the bus driver, not the function driver, should determine the value of the <b>Removable</b> parameter of the device. For USB devices, the USB hub driver sets the <b>Removable</b> parameter. It should not be modified by the function driver.

If <b>Removable</b> is set to <b>TRUE</b>, the device is displayed in the <b>Unplug or Eject Hardware</b> program, unless <b>SurpriseRemovalOK</b> is also set to <b>TRUE</b>.


### -field DockDevice

Specifies whether the device is a docking peripheral.


### -field UniqueID

Specifies whether the device's instance ID is unique system-wide. This bit is clear if the instance ID is unique only within the scope of the bus. For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/install/device-identification-strings">Device Identification Strings</a>.


### -field SilentInstall

Specifies whether Device Manager should suppress all installation dialog boxes; except required dialog boxes such as "no compatible drivers found."


### -field RawDeviceOK

Specifies whether the driver for the underlying bus can drive the device if there is no function driver (for example, SCSI devices in pass-through mode). This mode of operation is called <a href="https://msdn.microsoft.com/004698f5-cb0e-4995-a19c-7075aa226000">raw mode</a>.


### -field SurpriseRemovalOK

Specifies whether the function driver for the device can handle the case where the device is removed before Windows can send <b>IRP_MN_QUERY_REMOVE_DEVICE</b> to it. If <b>SurpriseRemovalOK</b> is set to <b>TRUE</b>, the device can be safely removed from its immediate parent regardless of the state that its driver is in.

For example, a standard USB mouse does not maintain any state in its hardware and thus can be safely removed at any time. However, an external hard disk whose driver caches writes in memory cannot be safely removed without first letting the driver flush its cache to the hardware.
<div class="alert"><b>Note</b>  Drivers for USB devices that support surprise removal must set this to <b>TRUE</b> only when the IRP is being passed back up the driver stack.</div><div> </div>

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

The PnP manager sends one <b>IRP_MN_QUERY_CAPABILITIES</b> IRP right after a device is enumerated and sends another after the device has been started. The PnP manager only checks this bit right after the device is enumerated. Once the device is started, this bit is ignored.


### -field NonDynamic

Reserved for future use.


### -field WarmEjectSupported

Reserved for future use.


### -field NoDisplayInUI

Do not display the device in the user interface. If this bit is set, the device is <u>never</u> displayed in the user interface, even if the device is present but fails to start. Only bus drivers and associated bus filter drivers should set this bit. (Also see the <b>PNP_DEVICE_DONT_DISPLAY_IN_UI</b> flag in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559618">PNP_DEVICE_STATE</a> structure.)


### -field Reserved1



### -field WakeFromInterrupt

 


### -field SecureDevice

 


### -field Reserved

Reserved for system use.


### -field Address

Specifies an address indicating where the device is located on its underlying bus.

The interpretation of this number is bus-specific. If the address is unknown or the bus driver does not support an address, the bus driver leaves this member at its default value of 0xFFFFFFFF.

The following list describes the information certain bus drivers store in the <b>Address</b> field for their child devices:




#### 1394

Does not supply an address because the addresses are volatile. Defaults to 0xFFFFFFFF. 


#### EISA

Slot Number (0-F).


#### IDE

For an IDE device, the address contains the target ID and LUN. For an IDE channel, the address is zero or one (0 = primary channel and 1 = secondary channel).


#### ISApnp

Does not supply an address. Defaults to 0xFFFFFFFF.


#### PC Card (PCMCIA)

The socket number (typically 0x00 or 0x40).


#### PCI

The device number in the high word and the function number in the low word.


#### SCSI

The target ID.


#### USB

The port number.


### -field UINumber

Specifies a number associated with the device that can be displayed in the user interface.

This number is typically a user-perceived slot number, such as a number printed next to the slot on the board, or some other number that makes locating the physical device easier for the user. For buses with no such convention, or when the <b>UINumber</b> is unknown, the bus driver leaves this member at its default value of 0xFFFFFFFF.


### -field DeviceState

An array of values indicating the most-powered device power state that the device can maintain for each system power state. The <b>DeviceState[PowerSystemWorking]</b> element of the array corresponds to the S0 system state. The entry for <b>PowerSystemUnspecified</b> is reserved for system use.

The entries in this array are based on the capabilities of the parent devnode. As a general rule, a driver should not change these values. However, if necessary, a driver can lower the value, for example, from <b>PowerDeviceD1</b> to <b>PowerDeviceD2</b>.

If the bus driver is unable to determine the appropriate device power state for a root-enumerated device, it sets <b>DeviceState[PowerSystemWorking]</b> to <b>PowerDeviceD0</b> and all other entries to <b>PowerDeviceD3</b>.


### -field SystemWake

Specifies the least-powered system power state from which the device can signal a wake event. A value of <b>PowerSystemUnspecified</b> indicates that the device cannot wake the system.

A bus driver can get this information from its parent devnode. 

In general, a driver should not change this value. If necessary, however, a driver can raise the power state, for example, from <b>PowerSystemHibernate</b> to <b>PowerSystemS1</b>, to indicate that its device cannot wake the system from a hibernation state but can from a higher-powered sleep state.


### -field DeviceWake

Specifies the least-powered device power state from which the device can signal a wake event. A value of <b>PowerDeviceUnspecified</b> indicates that the device cannot signal a wake event.


### -field D1Latency

Specifies the device's approximate worst-case latency, in 100-microsecond units, for returning the device to the <b>PowerDeviceD0</b> state from the <b>PowerDeviceD1</b> state. Set to zero if the device does not support the D1 state.


### -field D2Latency

Specifies the device's approximate worst-case latency, in 100-microsecond units, for returning the device to the <b>PowerDeviceD0</b> state from the <b>PowerDeviceD2</b> state. Set to zero if the device does not support the D2 state.


### -field D3Latency

Specifies the device's approximate worst-case latency, in 100-microsecond units, for returning the device to the <b>PowerDeviceD0</b> state from the <b>PowerDeviceD3</b> state. Set to zero if the device does not support the D3 state. 


## -remarks


Bus drivers set the appropriate values in this structure in response to an <b>IRP_MN_QUERY_CAPABILITIES</b> IRP. Bus filter drivers, function drivers, and filter drivers might alter the capabilities set by the bus driver.

Drivers that send an <b>IRP_MN_QUERY_CAPABILITIES</b> request must initialize the <b>Size</b>, <b>Version</b>, <b>Address</b>, and <b>UINumber</b> members of this structure before sending the IRP. 

For more information about using the <b>DEVICE_CAPABILITIES</b> structure to describe a device's power capabilities, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561058">Reporting Device Power Capabilities</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551664">IRP_MN_QUERY_CAPABILITIES</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559618">PNP_DEVICE_STATE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20DEVICE_CAPABILITIES structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

