---
UID: NF:wdm.IoGetDeviceProperty
title: IoGetDeviceProperty function (wdm.h)
description: The IoGetDeviceProperty routine retrieves information about a device such as configuration information and the name of its PDO.
old-location: kernel\iogetdeviceproperty.htm
tech.root: kernel
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

### -param DeviceObject [in]

Pointer to the physical device object (PDO) for the device being queried.

### -param DeviceProperty [in]

A [DEVICE_REGISTRY_PROPERTY](./ne-wdm-device_registry_property.md)-typed enumerator that identifies the device property to be retrieved.

### -param BufferLength [in]


Specifies the size, in bytes, of the caller-supplied *PropertyBuffer*.

### -param PropertyBuffer [out, optional]


Pointer to a caller-supplied buffer to receive the property information. The buffer can be allocated from pageable memory. The type of the buffer is determined by the *DeviceProperty* (see above).

### -param ResultLength [out]


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

[GUID](/windows-hardware/customize/desktop/unattend/microsoft-windows-shell-setup-notificationarea-promotedicon2-guid)

[INTERFACE_TYPE](ne-wdm-_interface_type.md)

[IO_RESOURCE_REQUIREMENTS_LIST](ns-wdm-_io_resource_requirements_list.md)
