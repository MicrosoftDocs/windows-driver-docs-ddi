---
UID: NS:storport._VIRTUAL_HW_INITIALIZATION_DATA
title: VIRTUAL_HW_INITIALIZATION_DATA (storport.h)
description: The VIRTUAL_HW_INITIALIZATION_DATA structure contains information particular to each virtual miniport driver.
old-location: storage\virtual_hw_initialization_data.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["VIRTUAL_HW_INITIALIZATION_DATA structure"]
ms.keywords: "*PVIRTUAL_HW_INITIALIZATION_DATA, PVIRTUAL_HW_INITIALIZATION_DATA, PVIRTUAL_HW_INITIALIZATION_DATA structure pointer [Storage Devices], VIRTUAL_HW_INITIALIZATION_DATA, VIRTUAL_HW_INITIALIZATION_DATA structure [Storage Devices], _VIRTUAL_HW_INITIALIZATION_DATA, storage.virtual_hw_initialization_data, storport/PVIRTUAL_HW_INITIALIZATION_DATA, storport/VIRTUAL_HW_INITIALIZATION_DATA, structs-virtual_afc3c543-a34f-4853-b67b-06d57d0350b6.xml"
req.header: storport.h
req.include-header: Storport.h
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
req.typenames: VIRTUAL_HW_INITIALIZATION_DATA, *PVIRTUAL_HW_INITIALIZATION_DATA
f1_keywords:
 - _VIRTUAL_HW_INITIALIZATION_DATA
 - storport/_VIRTUAL_HW_INITIALIZATION_DATA
 - PVIRTUAL_HW_INITIALIZATION_DATA
 - storport/PVIRTUAL_HW_INITIALIZATION_DATA
 - VIRTUAL_HW_INITIALIZATION_DATA
 - storport/VIRTUAL_HW_INITIALIZATION_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - VIRTUAL_HW_INITIALIZATION_DATA
---

# VIRTUAL_HW_INITIALIZATION_DATA structure

## -description

The **VIRTUAL_HW_INITIALIZATION_DATA** structure contains information particular to each virtual miniport driver.

## -struct-fields

### -field HwInitializationDataSize

Specifies the size of this structure in bytes, as returned by **sizeof**(). This member indicates the version of this structure that is used by the virtual miniport driver. A virtual miniport driver's **DriverEntry** routine should set this member's value for the port driver.

### -field AdapterInterfaceType

For storport virtual miniport drivers, the value for **AdapterInterfaceType** will almost always be **internal**. This is because the Storport driver does not support legacy buses.

Note that because of this, most of the adapter interface types that are used with the SCSI port driver are invalid for Storport drivers. In particular, Storport does not support:

* Isa
* Eisa
* MicroChannel
* TurboChannel

Additionally, unlike the SCSI port case, a virtual miniport driver that works with the Storport driver is not required to supply values for the following members:

* **VendorIdLength**
* **VendorId**
* **DeviceIdLength**
* **DeviceId**

### -field HwInitialize

A pointer to the virtual miniport driver's [**HwStorInitialize**](nc-storport-hw_initialize.md) routine, which is a required entry point for all virtual miniport drivers.

### -field HwStartIo

A pointer to the virtual miniport driver's [**HwStorStartIo**](nc-storport-hw_startio.md) routine, which is a required entry point for all virtual miniport drivers.

### -field HwInterrupt

Not used. Virtual miniport drivers do not process interrupts.

### -field HwFindAdapter

A pointer to the virtual miniport driver's [**VirtualHwStorFindAdapter**](nc-storport-virtual_hw_find_adapter.md) routine, which is a required entry point for all virtual miniport drivers.

### -field HwResetBus

A pointer to the virtual miniport driver's [**HwStorResetBus**](nc-storport-hw_reset_bus.md) routine, which is a required entry point for all virtual miniport drivers.

### -field HwDmaStarted

Not used. Virtual miniport drivers do not perform DMA.

### -field HwAdapterState

The Storport driver does not support legacy drivers. Therefore, this member must be **NULL**.

### -field DeviceExtensionSize

Specifies the size, in bytes, that is required by the virtual miniport driver for its per-adapter non-paged device extension. A virtual miniport driver uses its device extension as storage for driver-determined adapter information. The operating system-specific port driver initializes each device extension that it allocates with zeros, and passes a pointer to the adapter-specific device extension in most calls to the virtual miniport driver. The given size does not include any virtual miniport driver-requested per-logical-unit storage.

### -field SpecificLuExtensionSize

Specifies the size, in bytes, that is required by the virtual miniport driver for its per-logical-unit non-paged storage, if any. A virtual miniport driver can use its logical unit (LU) extensions as storage for driver-determined LU information about peripherals on the virtual bus. The operating system-specific port driver initializes each LU extension that it allocates with zeros. Leave this member set to zero if the virtual miniport driver does not maintain per-LU information for which it requires storage.

### -field SrbExtensionSize

Specifies the size, in bytes, that is required by the virtual miniport driver for its per-request non-paged storage, if any. Because virtual miniport drivers that work with the Storport driver must support scatter/gather lists, and the per-SRB scatter/gather lists are usually allocated in the SRB extension, this member is rarely zero.

### -field NumberOfAccessRanges

Not used. Virtual miniport drivers do not support hardware.

### -field Reserved

Reserved for system use.

### -field MapBuffers

| Name | Description |
| -- | -- |
| STOR_MAP_NO_BUFFERS | Only maps buffer for SRB_FUNCTION_IO_CONTROL and SRB_FUNCTION_WMI. |
| STOR_MAP_ALL_BUFFERS | Obsolete, same behavior as STOR_MAP_NON_READ_WRITE_BUFFERS. |
| STOR_MAP_NON_READ_WRITE_BUFFERS | Maps buffer for IO requests except READ and WRITE. |
| STOR_MAP_ALL_BUFFERS_INCLUDING_READ_WRITE | Maps buffer for all IO requests including READ and WRITE. Miniport drivers will typically use this setting. |

### -field NeedPhysicalAddresses

Not used. Virtual miniport drivers do not support hardware.

### -field TaggedQueuing

Must be set to **TRUE**. A value of **TRUE** indicates that the virtual miniport driver supports tagged queuing.

### -field AutoRequestSense

Must be set to **TRUE**. A value of **TRUE** indicates that the HBA can perform a request-sense operation without requiring an explicit request to do so.

### -field MultipleRequestPerLu

Must be set to **TRUE**. A value of **TRUE** indicates that the virtual miniport driver can queue multiple requests per logical unit (LU).

### -field ReceiveEvent

This value is no longer used, and can be set to either **TRUE** or **FALSE**.

### -field VendorIdLength

The length, in bytes, of the vendor identifier.

### -field VendorId

The vendor identifier.

### -field ReservedUshort

Reserved.

### -field PortVersionFlags

A bitmap of flags that indicate the features that the port driver supports. Currently, the only flag available is SP_VER_TRACE_SUPPORT, which indicates that the port driver supports tracing.

### -field DeviceIdLength

The length, in bytes, of the device identifier.

### -field DeviceId

The device identifier.

### -field HwAdapterControl

A pointer to the virtual miniport driver's [**HwStorAdapterControl**](nc-storport-hw_adapter_control.md) routine.

### -field HwBuildIo

This member is not used.

### -field HwFreeAdapterResources

A pointer to the virtual miniport driver's [**HwStorFreeAdapterResources**](nc-storport-hw_free_adapter_resources.md) routine, which is a required entry point for all virtual miniport drivers.

### -field HwProcessServiceRequest

A pointer to the virtual miniport driver's [**HwStorProcessServiceRequest**](nc-storport-hw_process_service_request.md) routine.

### -field HwCompleteServiceIrp

A pointer to the virtual miniport driver's [**HwStorCompleteServiceIrp**](nc-storport-hw_complete_service_irp.md) routine.

### -field HwInitializeTracing

A pointer to the virtual miniport driver's [**HwStorInitializeTracing**](nc-storport-hw_initialize_tracing.md) routine.

### -field HwCleanupTracing

A pointer to the virtual miniport driver's [**HwStorCleanupTracing**](nc-storport-hw_cleanup_tracing.md) routine.

## -remarks

If a virtual miniport driver will execute only on Windows 8 or later, the driver should use the [**HW_INITIALIZATION_DATA**](ns-storport-_hw_initialization_data-r1.md) structure instead of **VIRTUAL_HW_INITIALIZATION_DATA**.

## -see-also

[**HwStorAdapterControl**](nc-storport-hw_adapter_control.md)

[**HwStorCleanupTracing**](nc-storport-hw_cleanup_tracing.md)

[**HwStorCompleteServiceIrp**](nc-storport-hw_complete_service_irp.md)

[**HwStorFreeAdapterResources**](nc-storport-hw_free_adapter_resources.md)

[**HwStorInitialize**](nc-storport-hw_initialize.md)

[**HwStorInitializeTracing**](nc-storport-hw_initialize_tracing.md)

[**HwStorProcessServiceRequest**](nc-storport-hw_process_service_request.md)

[**HwStorResetBus**](nc-storport-hw_reset_bus.md)

[**HwStorStartIo**](nc-storport-hw_startio.md)

[**VirtualHwStorFindAdapter**](nc-storport-virtual_hw_find_adapter.md)
