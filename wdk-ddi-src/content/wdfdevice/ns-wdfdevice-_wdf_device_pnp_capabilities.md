---
UID: NS:wdfdevice._WDF_DEVICE_PNP_CAPABILITIES
title: "_WDF_DEVICE_PNP_CAPABILITIES"
author: windows-driver-content
description: The WDF_DEVICE_PNP_CAPABILITIES structure describes a device's Plug and Play capabilities.
old-location: wdf\wdf_device_pnp_capabilities.htm
old-project: wdf
ms.assetid: 0857e32e-9962-44ca-9d61-b98b09073c16
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDF_DEVICE_PNP_CAPABILITIES, DFDeviceObjectGeneralRef_58325ea6-665b-4cf2-bf99-d47636013ee1.xml, PWDF_DEVICE_PNP_CAPABILITIES, PWDF_DEVICE_PNP_CAPABILITIES structure pointer, WDF_DEVICE_PNP_CAPABILITIES, WDF_DEVICE_PNP_CAPABILITIES structure, _WDF_DEVICE_PNP_CAPABILITIES, kmdf.wdf_device_pnp_capabilities, wdf.wdf_device_pnp_capabilities, wdfdevice/PWDF_DEVICE_PNP_CAPABILITIES, wdfdevice/WDF_DEVICE_PNP_CAPABILITIES"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfdevice.h
api_name:
-	WDF_DEVICE_PNP_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_PNP_CAPABILITIES, *PWDF_DEVICE_PNP_CAPABILITIES
---

# _WDF_DEVICE_PNP_CAPABILITIES structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The WDF_DEVICE_PNP_CAPABILITIES structure describes a device's Plug and Play capabilities.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field LockSupported

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff552533">WDF_TRI_STATE</a>-typed value that indicates, if set to <b>WdfTrue</b>, that the device can be locked in its slot to prevent ejection. (This capability disables ejecting a device from its slot, not ejecting media from a device.) For more information about WDF_TRI_STATE-typed values, see the following Remarks section.  


### -field EjectSupported

A WDF_TRI_STATE-typed value that indicates, if set to <b>WdfTrue</b>, that the device can be ejected from its slot. (This capability enables ejecting a device from its slot, not ejecting media from a device.) 


### -field Removable

A WDF_TRI_STATE-typed value that indicates, if set to <b>WdfTrue</b>, that the device can be removed while the system is running. If <b>Removable</b> is set to <b>WdfTrue</b> and <b>SurpriseRemovalOK</b> is set to <b>WdfFalse</b>, users should use the system's Unplug or Eject Hardware program.


### -field DockDevice

A WDF_TRI_STATE-typed value that indicates, if set to <b>WdfTrue</b>, that the device is a docking station.


### -field UniqueID

A WDF_TRI_STATE-typed value that indicates, if set to <b>WdfTrue</b>, that the device's instance ID is unique to the entire system. If <b>UniqueID</b> is set to <b>WdfFalse</b>, the instance ID is unique only to the device's bus. For more information about instance IDs, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/install/device-identification-strings">Device Identification Strings</a>.


### -field SilentInstall

A WDF_TRI_STATE-typed value that indicates, if set to <b>WdfTrue</b>, that Device Manager should not display dialog boxes during installation of the device.


### -field SurpriseRemovalOK

A WDF_TRI_STATE-typed value that indicates, if set to <b>WdfTrue</b> (and if <b>Removable</b> is also set to <b>WdfTrue</b>), that users can remove the device without using the system's Unplug or Eject Hardware program.


### -field HardwareDisabled

A WDF_TRI_STATE-typed value that indicates, if set to <b>WdfTrue</b>, that the device is disabled.


### -field NoDisplayInUI

A WDF_TRI_STATE-typed value that indicates, if set to <b>WdfTrue</b>, that Device Manager should not display the device.


### -field Address

An address that indicates where the device is located on its bus. 

The interpretation of this number is bus-specific. If the address is unknown or the bus driver does not support an address, the bus driver leaves the <b>Address</b> member at its default value of 0xFFFFFFFF (-1).

The following list describes the information that certain bus drivers store in the <b>Address</b> member for their child devices:





#### 1394

Does not supply an address because the addresses are volatile. Defaults to 0xFFFFFFFF. 



#### EISA

Slot Number (0-F).



#### IDE

For an IDE device, the address contains the target ID and LUN. For an IDE channel, the address is 0 if the channel is the primary channel or 1 if the channel is the secondary channel).



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

A number that is associated with the device and can be displayed in user interfaces. This number is typically a user-perceived slot number, such as a number printed next to the slot on the board or some other number that helps the user locate the device. If <b>UINumber</b> is unknown, or if supplying a number would not assist the user in identifying the device's location, the driver sets this value to -1.


## -remarks



Several members use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552533">WDF_TRI_STATE</a> type. For these members, a value of <b>WdfTrue</b> indicates that the device supports the capability and a value of <b>WdfFalse</b> indicates it does not. A value of <b>WdfUseDefault</b> indicates the framework will use the value that a driver lower in the stack provided. For example, if a bus driver specifies <b>WdfTrue</b> for <b>LockSupported</b> and the device's function driver specifies <b>WdfUseDefault</b>, the framework stores <b>WdfTrue</b> for the capability.

The WDF_DEVICE_PNP_CAPABILITIES structure is used as input to <a href="https://msdn.microsoft.com/library/windows/hardware/ff546898">WdfDeviceSetPnpCapabilities</a>.

To initialize a WDF_DEVICE_PNP_CAPABILITIES structure, a driver should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff551259">WDF_DEVICE_PNP_CAPABILITIES_INIT</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546901">WdfDeviceSetPowerCapabilities</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548802">WdfPdoInitAssignRawDevice</a>
 

 

