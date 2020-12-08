---
UID: NF:storport.StorPortGetBusData
title: StorPortGetBusData function (storport.h)
description: The StorPortGetBusData routine retrieves the bus-specific configuration information necessary to initialize the HBA.
old-location: storage\storportgetbusdata.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["StorPortGetBusData function"]
ms.keywords: StorPortGetBusData, StorPortGetBusData routine [Storage Devices], storage.storportgetbusdata, storport/StorPortGetBusData, storprt_fb8cc730-c53e-49b6-abe5-6a0648200d32.xml
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
req.lib: Storport.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortGetBusData
 - storport/StorPortGetBusData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Storport.lib
 - Storport.dll
api_name:
 - StorPortGetBusData
---

# StorPortGetBusData function

## -description

The **StorPortGetBusData** routine retrieves the bus-specific configuration information necessary to initialize the HBA.

## -parameters

### -param DeviceExtension

[in] Pointer to the miniport driver's per-HBA storage area.

### -param BusDataType

[in] Contains a value of type [**BUS_DATA_TYPE**](../ntddk/ne-ntddk-_bus_data_type.md) that specifies the type of bus-specific configuration data to be returned. Currently, this value can be one of the following: **Cmos**, **EisaConfiguration**, **Pos**, or **PCIConfiguration**. However, additional types of bus configuration will be supported in the future. The upper bound on the types supported is always **MaximumBusDataType**.

### -param SystemIoBusNumber

[in] Specifies the system-assigned number of the I/O bus. The miniport driver's [**HwStorFindAdapter**](nc-storport-hw_find_adapter.md) routine obtains this value from the **SystemIoBusNumber** member initially set in [**PORT_CONFIGURATION_INFORMATION**](ns-storport-_port_configuration_information.md).

### -param SlotNumber

[in] Specifies the logical slot number or location of the device.

If **PCIConfiguration** is specified as the *BusDataType*, this parameter must be specified as a PCI_SLOT_NUMBER-type value.

### -param Buffer

[in, out] Pointer to a buffer or area to which the configuration data is returned or, if the given *Length* is zero, points to a location to which the OS-specific port driver returns a pointer to a buffer that it allocates.

### -param Length

[in] Specifies the maximum number of bytes to return at *Buffer*, or zero if the caller requires the OS-specific port driver to allocate a buffer to contain the data.

## -returns

**StorPortGetBusData** returns the number of bytes of configuration information it stored in the buffer. When the input *BusDataType* is **PCIConfiguration**, **StorPortGetBusData** can return either of the following values to indicate an error.

| Return code  | Description |
| -----------  | ----------- |
| **0 (zero)** | The PCI bus does not exist. |
| **2**        | The PCI bus exists, but there is no device at the given PCI *SlotNumber*. The *Buffer* contains the value PCI_INVALID_VENDOR_ID at the PCI_COMMON_CONFIG **VendorId** member. |

## -remarks

**StorPortGetBusData** can be called only from a miniport driver's [**HwStorAdapterControl**](nc-storport-hw_adapter_control.md) when the control type is **ScsiSetRunningConfig**. Calls from other miniport driver routines will result in system failure or incorrect operation for the caller.

Configuration data returned by **StorPortGetBusData** is valid only until the miniport driver calls **StorPortGetBusData** again. As soon as the caller's [**HwStorFindAdapter**](nc-storport-hw_find_adapter.md) routine returns control, any returned configuration data becomes invalid.

## -see-also

[**HwStorFindAdapter**](nc-storport-hw_find_adapter.md)

[**PORT_CONFIGURATION_INFORMATION**](ns-storport-_port_configuration_information.md)
