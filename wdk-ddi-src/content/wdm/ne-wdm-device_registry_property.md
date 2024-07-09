---
UID: NE:wdm.DEVICE_REGISTRY_PROPERTY
title: DEVICE_REGISTRY_PROPERTY (wdm.h)
description: The DEVICE_REGISTRY_PROPERTY enumeration identifies device properties that are stored in the registry.
old-location: kernel\device_registry_property.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["DEVICE_REGISTRY_PROPERTY enumeration"]
ms.keywords: DEVICE_REGISTRY_PROPERTY, DEVICE_REGISTRY_PROPERTY Enumeration, DEVICE_REGISTRY_PROPERTY enumeration [Kernel-Mode Driver Architecture], DevicePropertyAddress, DevicePropertyAllocatedResources, DevicePropertyBootConfiguration, DevicePropertyBootConfigurationTranslated, DevicePropertyBusNumber, DevicePropertyBusTypeGuid, DevicePropertyClassGuid, DevicePropertyClassName, DevicePropertyCompatibleIDs, DevicePropertyContainerID, DevicePropertyDeviceDescription, DevicePropertyDriverKeyName, DevicePropertyEnumeratorName, DevicePropertyFriendlyName, DevicePropertyHardwareID, DevicePropertyInstallState, DevicePropertyLegacyBusType, DevicePropertyLocationInformation, DevicePropertyManufacturer, DevicePropertyPhysicalDeviceObjectName, DevicePropertyRemovalPolicy, DevicePropertyResourceRequirements, DevicePropertyUINumber, enumeration [Kernel-Mode Driver Architecture], kernel.device_registry_property, sysenum_485e3369-186a-4a71-b13e-be6ff9ab8dce.xml, wdm/, wdm/DevicePropertyAddress, wdm/DevicePropertyAllocatedResources, wdm/DevicePropertyBootConfiguration, wdm/DevicePropertyBootConfigurationTranslated, wdm/DevicePropertyBusNumber, wdm/DevicePropertyBusTypeGuid, wdm/DevicePropertyClassGuid, wdm/DevicePropertyClassName, wdm/DevicePropertyCompatibleIDs, wdm/DevicePropertyContainerID, wdm/DevicePropertyDeviceDescription, wdm/DevicePropertyDriverKeyName, wdm/DevicePropertyEnumeratorName, wdm/DevicePropertyFriendlyName, wdm/DevicePropertyHardwareID, wdm/DevicePropertyInstallState, wdm/DevicePropertyLegacyBusType, wdm/DevicePropertyLocationInformation, wdm/DevicePropertyManufacturer, wdm/DevicePropertyPhysicalDeviceObjectName, wdm/DevicePropertyRemovalPolicy, wdm/DevicePropertyResourceRequirements, wdm/DevicePropertyUINumber
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Wudfwdm.h
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
req.typenames: DEVICE_REGISTRY_PROPERTY
f1_keywords:
 - DEVICE_REGISTRY_PROPERTY
 - wdm/DEVICE_REGISTRY_PROPERTY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - DEVICE_REGISTRY_PROPERTY
---

# DEVICE_REGISTRY_PROPERTY enumeration

## -description

The <b>DEVICE_REGISTRY_PROPERTY</b> enumeration identifies device properties that are stored in the registry.

## -enum-fields

### -field DevicePropertyDeviceDescription

String describing the device, such as "Microsoft PS/2 Port Mouse", typically defined by the manufacturer. Property type is a NULL-terminated WCHAR string. 

### -field DevicePropertyHardwareID

[Hardware IDs](/windows-hardware/drivers/install/hardware-ids) provided by the device that identify the device. Property type is a REG_MULTI_SZ value.

### -field DevicePropertyCompatibleIDs

[Compatible IDs](/windows-hardware/drivers/install/compatible-ids) reported by the device. Property type is a REG_MULTI_SZ value.

### -field DevicePropertyBootConfiguration

Hardware resources assigned to the device by the firmware, in raw form. Property type is a [CM_RESOURCE_LIST](./ns-wdm-_cm_resource_list.md) structure.

### -field DevicePropertyBootConfigurationTranslated

The hardware resources assigned to the device by the firmware, in translated form. Property type is a **CM_RESOURCE_LIST** structure.

### -field DevicePropertyClassName

Name of the device's setup class, in text format. Property type is a NULL-terminated WCHAR string. 

### -field DevicePropertyClassGuid

GUID for the device's setup class. Property type is a NULL-terminated array of WCHAR.

The GUID in a string format as follows, where each "c" represents a hexadecimal character: {cccccccc-cccc-cccc-cccc-cccccccccccc}

### -field DevicePropertyDriverKeyName

Name of the driver-specific registry key. Property type is a NULL-terminated WCHAR string.

### -field DevicePropertyManufacturer

String identifying the manufacturer of the device. Property type is a NULL-terminated WCHAR string.

### -field DevicePropertyFriendlyName

String that can be used to distinguish between two similar devices, typically defined by the class installer. Property type is a NULL-terminated WCHAR string.

### -field DevicePropertyLocationInformation

Information about the device's location on the bus; the interpretation of this information is bus-specific. Property type is a NULL-terminated WCHAR string.

### -field DevicePropertyPhysicalDeviceObjectName

Name of the PDO for this device. Property type is a NULL-terminated WCHAR string.

### -field DevicePropertyBusTypeGuid

GUID for the bus that the device is connected to. The system-defined bus type GUIDs are listed in the `Wdmguid.h` header file. Property type is a GUID, which is a 16-byte structure that contains the GUID in binary form.

### -field DevicePropertyLegacyBusType

Requests the bus type, such as PCIBus or PCMCIABus. Property type is an [INTERFACE_TYPE](ne-wdm-_interface_type.md) enumeration value.

### -field DevicePropertyBusNumber

Legacy bus number of the bus the device is connected to. Property type is a ULONG.

### -field DevicePropertyEnumeratorName

Name of the enumerator for the device, such as "PCI" or "root". Property type is a NULL-terminated WCHAR string.

### -field DevicePropertyAddress

Address of the device on the bus. Property type is a ULONG.

The interpretation of this address is bus-specific. The caller of this routine should call the routine again to request the **DevicePropertyBusTypeGuid**, or possibly the **DevicePropertyLegacyBusType**, so it can interpret the address. An address value of 0xFFFFFFFF indicates that the underlying bus driver did not supply a bus address for the device.

The following list describes the information certain bus drivers store for their child devices:

| Bus | Description |
|-----|-------------|
| 1394 | Does not supply an address because the addresses are volatile. Defaults to 0xFFFFFFFF. |
| EISA | Slot Number (0-F). |
| IDE | For an IDE device, the address contains the target ID and LUN. For an IDE channel, the address is zero or one (0 = primary channel and 1 = secondary channel). |
| ISApnp | Does not supply an address. Defaults to 0xFFFFFFFF. |
| PC Card (PCMCIA) | The socket number (typically 0x00 or 0x40). |
| PCI | The device number in the high word and the function number in the low word. |
| SCSI | The target ID. |
| USB | The port number. |

### -field DevicePropertyUINumber

Number associated with the device that can be displayed in the user interface. Property type is a ULONG value.

This number is typically a user-perceived slot number, such as a number printed next to the slot on the board, or some other number that makes locating the physical device easier for the user. If the device is on a bus that has no UI number convention, or if the bus driver for the device cannot determine the UI number, this value is 0xFFFFFFFF.

### -field DevicePropertyInstallState

Device's installation state. Property type is a [DEVICE_INSTALL_STATE](ne-wdm-_device_install_state.md) enumeration value.

### -field DevicePropertyRemovalPolicy

Device's current removal policy. The operating system uses this value as a hint to determine how the device is normally removed. Property type is a [DEVICE_REMOVAL_POLICY](ne-wdm-_device_removal_policy.md) enumeration value.

### -field DevicePropertyResourceRequirements

### -field DevicePropertyAllocatedResources

### -field DevicePropertyContainerID

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdeviceproperty">IoGetDeviceProperty</a>

