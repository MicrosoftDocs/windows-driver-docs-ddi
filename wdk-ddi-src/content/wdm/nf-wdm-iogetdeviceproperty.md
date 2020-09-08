---
UID: NF:wdm.IoGetDeviceProperty
title: IoGetDeviceProperty function (wdm.h)
description: The IoGetDeviceProperty routine retrieves information about a device such as configuration information and the name of its PDO.
old-location: kernel\iogetdeviceproperty.htm
tech.root: kernel
ms.assetid: 8c3b7f81-ea6e-47ae-a396-58826d097f1f
ms.date: 04/30/2018
keywords: ["IoGetDeviceProperty function"]
ms.keywords: IoGetDeviceProperty, IoGetDeviceProperty routine [Kernel-Mode Driver Architecture], k104_b6185e0d-5e39-4671-ab50-07fe5eda3606.xml, kernel.iogetdeviceproperty, wdm/IoGetDeviceProperty
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoGetDeviceProperty
 - wdm/IoGetDeviceProperty
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoGetDeviceProperty
---

# IoGetDeviceProperty function


## -description

The **IoGetDeviceProperty** routine retrieves information about a device such as configuration information and the name of its PDO.

## -parameters

### -param DeviceObject 

[in]
Pointer to the physical device object (PDO) for the device being queried.

### -param DeviceProperty 

[in]
Specifies the device property being requested. Must be one of the following [DEVICE_REGISTRY_PROPERTY](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-device_registry_property) enumeration values:

#### DevicePropertyAddress

Requests the address of the device on the bus. *PropertyBuffer* points to a ULONG.

The interpretation of this address is bus-specific. The caller of this routine should call the routine again to request the **DevicePropertyBusTypeGuid**, or possibly the **DevicePropertyLegacyBusType**, so it can interpret the address. An address value of 0xFFFFFFFF indicates that the underlying bus driver did not supply a bus address for the device.

#### DevicePropertyBootConfiguration

Requests the hardware resources assigned to the device by the firmware, in raw form. *PropertyBuffer* points to a [CM_RESOURCE_LIST](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_resource_list) structure.

#### DevicePropertyBootConfigurationTranslated

The hardware resources assigned to the device by the firmware, in translated form. *PropertyBuffer* points to a **CM_RESOURCE_LIST** structure.

#### DevicePropertyBusNumber

Requests the legacy bus number of the bus the device is connected to. *PropertyBuffer* points to a ULONG.

#### DevicePropertyBusTypeGuid

Requests the GUID for the bus that the device is connected to. The system-defined bus type GUIDs are listed in the Wdmguid.h header file. *PropertyBuffer* points to a GUID, which is a 16-byte structure that contains the GUID in binary form.

#### DevicePropertyClassGuid

Requests the GUID for the device's setup class. *PropertyBuffer* points to a NULL-terminated array of WCHAR. This routine returns the GUID in a string format as follows, where each "c" represents a hexadecimal character: {cccccccc-cccc-cccc-cccc-cccccccccccc}

#### DevicePropertyClassName

Requests the name of the device's setup class, in text format. *PropertyBuffer* points to a NULL-terminated WCHAR string. 

#### DevicePropertyCompatibleIDs

Requests the [compatible IDs](https://docs.microsoft.com/windows-hardware/drivers/install/compatible-ids) reported by the device. *PropertyBuffer* points to a REG_MULTI_SZ value.

#### DevicePropertyDeviceDescription

Requests a string describing the device, such as "Microsoft PS/2 Port Mouse", typically defined by the manufacturer. *PropertyBuffer* points to a NULL-terminated WCHAR string. 

#### DevicePropertyDriverKeyName

Requests the name of the driver-specific registry key. *PropertyBuffer* points to a NULL-terminated WCHAR string.

#### DevicePropertyEnumeratorName

Requests the name of the enumerator for the device, such as "PCI" or "root". *PropertyBuffer* points to a NULL-terminated WCHAR string.

#### DevicePropertyFriendlyName

Requests a string that can be used to distinguish between two similar devices, typically defined by the class installer. *PropertyBuffer* points to a NULL-terminated WCHAR string.

#### DevicePropertyHardwareID

Requests the [hardware](https://docs.microsoft.com/windows-hardware/drivers/install/hardware-ids) IDs provided by the device that identify the device. *PropertyBuffer* points to a REG_MULTI_SZ value.

#### DevicePropertyInstallState

Requests the device's installation state. The installation state is returned as a [DEVICE_INSTALL_STATE](ne-wdm-_device_install_state.md) enumeration value.

#### DevicePropertyLegacyBusType

Requests the bus type, such as PCIBus or PCMCIABus. *PropertyBuffer* points to an [INTERFACE_TYPE](ne-wdm-_interface_type.md) enumeration value.

#### DevicePropertyLocationInformation

Requests information about the device's location on the bus; the interpretation of this information is bus-specific. *PropertyBuffer* points to a NULL-terminated WCHAR string.

#### DevicePropertyManufacturer

Requests a string identifying the manufacturer of the device. *PropertyBuffer* points to a NULL-terminated WCHAR string.

#### DevicePropertyPhysicalDeviceObjectName

Requests the name of the PDO for this device. *PropertyBuffer* points to a NULL-terminated WCHAR string.

#### DevicePropertyRemovalPolicy

Requests the device's current removal policy. The operating system uses this value as a hint to determine how the device is normally removed. The *PropertyBuffer* parameter points to a [DEVICE_REMOVAL_POLICY](ne-wdm-_device_removal_policy.md) enumeration value.

#### DevicePropertyUINumber

Requests a number associated with the device that can be displayed in the user interface. *PropertyBuffer* points to a ULONG value.

This number is typically a user-perceived slot number, such as a number printed next to the slot on the board, or some other number that makes locating the physical device easier for the user. If the device is on a bus that has no UI number convention, or if the bus driver for the device cannot determine the UI number, this value is 0xFFFFFFFF.

### -param BufferLength 

[in]
Specifies the size, in bytes, of the caller-supplied *PropertyBuffer*.

### -param PropertyBuffer 

[out, optional]
Pointer to a caller-supplied buffer to receive the property information. The buffer can be allocated from pageable memory. The type of the buffer is determined by the *DeviceProperty* (see above).

### -param ResultLength 

[out]
Pointer to a ULONG to receive the size of the property information returned at *PropertyBuffer*. If **IoGetDeviceProperty** returns STATUS_BUFFER_TOO_SMALL, it sets this parameter to the required buffer length.

## -returns

**IoGetDeviceProperty** returns STATUS_SUCCESS if the call was successful. Possible error return values include the following.

|Return code|Description|
|----|----|
|**STATUS_BUFFER_TOO_SMALL**|The buffer at *PropertyBuffer* was too small. *ResultLength* points to the required buffer length.|
|**STATUS_INVALID_PARAMETER_2**|The given *DeviceProperty* is not one of the properties handled by this routine.|
|**STATUS_INVALID_DEVICE_REQUEST**|Possibly indicates that the given *DeviceObject* was not a valid PDO pointer.|

## -remarks

**IoGetDeviceProperty** retrieves device setup information from the registry. Use this routine, rather than accessing the registry directly, to insulate a driver from differences across platforms and from possible changes in the registry structure.

For many *DeviceProperty* requests, it can take two or more calls to **IoGetDeviceProperty** to determine the required *BufferLength*. The first call should use a best-guess value. If the return status is STATUS_BUFFER_TOO_SMALL, the driver should free its current buffer, allocate a buffer of the size returned in *ResultLength*, and call **IoGetDeviceProperty** again. Because some of the setup properties are dynamic, the data size can change between the time the required size is returned and driver calls this routine again. Therefore, drivers should call **IoGetDeviceProperty** inside a loop that runs until the return status is not STATUS_BUFFER_TOO_SMALL.

Function drivers that support devices on a legacy bus and a PnP bus can use the **DevicePropertyBusNumber**, **DevicePropertyBusTypeGuid**, and **DevicePropertyLegacyBusType** properties to distinguish between the buses.

## -see-also

[CM_RESOURCE_LIST](ns-wdm-_cm_resource_list.md)

[DEVICE_REMOVAL_POLICY](ne-wdm-_device_removal_policy.md)

[ExAllocatePoolWithTag](nf-wdm-exallocatepoolwithtag.md)

[GUID](https://docs.microsoft.com/windows-hardware/customize/desktop/unattend/microsoft-windows-shell-setup-notificationarea-promotedicon2-guid)

[INTERFACE_TYPE](ne-wdm-_interface_type.md)

[IO_RESOURCE_REQUIREMENTS_LIST](ns-wdm-_io_resource_requirements_list.md)

