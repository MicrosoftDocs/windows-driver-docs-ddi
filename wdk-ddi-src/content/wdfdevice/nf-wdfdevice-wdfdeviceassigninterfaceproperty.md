---
UID: NF:wdfdevice.WdfDeviceAssignInterfaceProperty
title: WdfDeviceAssignInterfaceProperty function (wdfdevice.h)
description: The WdfDeviceAssignInterfaceProperty method modifies the current value of a device interface property.
tech.root: wdf
ms.date: 07/14/2022
keywords: ["WdfDeviceAssignInterfaceProperty function"]
ms.keywords: WdfDeviceAssignInterfaceProperty, WdfDeviceAssignInterfaceProperty method, wdf.wdfdeviceassigninterfaceproperty, wdfdevice/WdfDeviceAssignInterfaceProperty
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: WUDFx02000.lib
req.dll: WUDFx02000.dll
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfDeviceAssignInterfaceProperty
 - wdfdevice/WdfDeviceAssignInterfaceProperty
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - WUDFx02000.dll
api_name:
 - WdfDeviceAssignInterfaceProperty
---

## -description

> [!IMPORTANT]
> Applies to UMDF only

The **WdfDeviceAssignInterfaceProperty** method modifies the current value of a [device interface property](/windows-hardware/drivers/install/accessing-device-interface-properties).

> [!NOTE]
> To retrieve or modify a device interface property, a KMDF driver must call [**IoGetDeviceInterfacePropertyData**](../wdm/nf-wdm-iogetdeviceinterfacepropertydata.md) or [**IoSetDeviceInterfacePropertyData**](../wdm/nf-wdm-iosetdeviceinterfacepropertydata.md) directly.

## -parameters

### -param Device [in]

A handle to a framework device object.

### -param PropertyData [in]

A pointer to [WDF_DEVICE_INTERFACE_PROPERTY_DATA](./ns-wdfdevice-_wdf_device_interface_property_data.md) structure.

### -param Type [in]

A **DEVPROPTYPE**-typed value that specifies the type of the data that is provided in *PropertyBuffer*.

### -param BufferLength [in]

Specifies the length, in bytes, of the buffer that *PropertyBuffer* points to.

### -param PropertyBuffer [in, optional]

A pointer to the device interface property data. Set this parameter to **NULL** to delete the specified property.

## -returns

If the **WdfDeviceAssignInterfaceProperty** method encounters no errors, it returns STATUS_SUCCESS. Additional return values include:

| Return code | Description |
|--|--|
| **STATUS_INVALID_PARAMETER** | One of the parameters is incorrect. |

The method might return other [NTSTATUS values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

For information about related methods, see [Accessing the Unified Device Property Model](/windows-hardware/drivers/wdf/accessing-the-unified-device-property-model).

### Examples

The following code example initializes a [WDF_DEVICE_INTERFACE_PROPERTY_DATA](./ns-wdfdevice-_wdf_device_interface_property_data.md) structure and then calls **WdfDeviceAssignInterfaceProperty**.

```cpp
DEFINE_DEVPROPKEY(DEVPKEY_ToasterCrispLevelDword, 0x5d0ba64a, 0x2396, 0x4bc9, 0xbf, 0x49, 0x52, 0x1d, 0xa6, 0x2b, 0x1b, 0xed, 3);  // DEVPROP_TYPE_UINT32

ULONG crispLevel = 0;
WDF_DEVICE_INTERFACE_PROPERTY_DATA propertyData;

WDF_DEVICE_INTERFACE_PROPERTY_DATA_INIT(
                          &propertyData, 
                          &GUID_DEVINTERFACE_TOASTER_DRIVER
                          &DEVPKEY_ToasterCrispLevelDword
                          );

status = WdfDeviceAssignInterfaceProperty(device, 
                                          &propertData,
                                          DEVPROP_TYPE_UINT32,
                                          sizeof(crispLevel),
                                          &crispLevel);
if (!NT_SUCCESS(status)) {
    return status;
}

```

## -see-also

[WDF_DEVICE_INTERFACE_PROPERTY_DATA](./ns-wdfdevice-_wdf_device_interface_property_data.md)

[WDF_DEVICE_INTERFACE_PROPERTY_DATA_INIT](./nf-wdfdevice-wdf_device_interface_property_data_init.md)

[WdfDeviceAllocAndQueryInterfaceProperty](./nf-wdfdevice-wdfdeviceallocandqueryinterfaceproperty.md)

[WdfDeviceQueryInterfaceProperty](./nf-wdfdevice-wdfdevicequeryinterfaceproperty.md)
