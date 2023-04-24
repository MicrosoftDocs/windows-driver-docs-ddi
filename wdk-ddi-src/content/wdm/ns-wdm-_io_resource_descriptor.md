---
UID: NS:wdm._IO_RESOURCE_DESCRIPTOR
title: IO_RESOURCE_DESCRIPTOR (wdm.h)
description: The _IO_RESOURCE_DESCRIPTOR structure (wdm.h) describes a range of raw hardware resources, of one type, that can be used by a device.
tech.root: kernel
ms.date: 12/15/2022
keywords: ["IO_RESOURCE_DESCRIPTOR structure"]
ms.keywords: "*PIO_RESOURCE_DESCRIPTOR, 0, CM_RESOURCE_CONNECTION_CLASS_GPIO, CM_RESOURCE_CONNECTION_CLASS_SERIAL, CM_RESOURCE_CONNECTION_TYPE_GPIO_IO, CM_RESOURCE_CONNECTION_TYPE_SERIAL_I2C, CM_RESOURCE_CONNECTION_TYPE_SERIAL_SPI, CM_RESOURCE_CONNECTION_TYPE_SERIAL_UART, CM_RESOURCE_INTERRUPT_LATCHED, CM_RESOURCE_INTERRUPT_LEVEL_SENSITIVE, CM_RESOURCE_INTERRUPT_MESSAGE, CM_RESOURCE_INTERRUPT_POLICY_INCLUDED, CM_RESOURCE_INTERRUPT_SECONDARY_INTERRUPT, CM_RESOURCE_INTERRUPT_WAKE_HINT, IO_RESOURCE_ALTERNATIVE, IO_RESOURCE_DEFAULT, IO_RESOURCE_DESCRIPTOR, IO_RESOURCE_DESCRIPTOR structure [Kernel-Mode Driver Architecture], IO_RESOURCE_PREFERRED, PIO_RESOURCE_DESCRIPTOR, PIO_RESOURCE_DESCRIPTOR structure pointer [Kernel-Mode Driver Architecture], _IO_RESOURCE_DESCRIPTOR, kernel.io_resource_descriptor, kstruct_b_6b096887-dd89-43b8-abb8-4f3582392573.xml, wdm/IO_RESOURCE_DESCRIPTOR, wdm/PIO_RESOURCE_DESCRIPTOR"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Miniport.h
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
req.typenames: IO_RESOURCE_DESCRIPTOR, *PIO_RESOURCE_DESCRIPTOR
f1_keywords:
 - _IO_RESOURCE_DESCRIPTOR
 - wdm/_IO_RESOURCE_DESCRIPTOR
 - PIO_RESOURCE_DESCRIPTOR
 - wdm/PIO_RESOURCE_DESCRIPTOR
 - IO_RESOURCE_DESCRIPTOR
 - wdm/IO_RESOURCE_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _IO_RESOURCE_DESCRIPTOR
 - PIO_RESOURCE_DESCRIPTOR
 - IO_RESOURCE_DESCRIPTOR
---

## -description

The **IO_RESOURCE_DESCRIPTOR** structure describes a range of raw hardware resources, of one type, that can be used by a device. An array of **IO_RESOURCE_DESCRIPTOR** structures is contained within each [**IO_RESOURCE_LIST**](./ns-wdm-_io_resource_list.md) structure.

## -struct-fields

### -field Option

Specifies whether this resource description is required, preferred, or alternative. One of the following values must be used:

| Value | Meaning |
|---|---|
| 0 | The specified resource range is required, unless alternative ranges are also specified. |
| IO_RESOURCE_PREFERRED | The specified resource range is preferred to any alternative ranges. |
| IO_RESOURCE_ALTERNATIVE | The specified resource range is an alternative to the range preceding it. For example, if one **IO_RESOURCE_DESCRIPTOR** structure specifies IRQ 5, with IO_RESOURCE_PREFERRED set, and the next structure specifies IRQ 3, with IO_RESOURCE_ALTERNATIVE set, the PnP manager assigns IRQ 3 to the device only if IRQ 5 is unavailable. Multiple alternatives can be specified for each resource. Both IO_RESOURCE_ALTERNATIVE and IO_RESOURCE_PREFERRED can be set, indicating a preferred alternative. |
| IO_RESOURCE_DEFAULT | Not used. |

### -field Type

Identifies the resource type. For a list of valid values, see the **Type** member of the [**CM_PARTIAL_RESOURCE_DESCRIPTOR**](./ns-wdm-_cm_partial_resource_descriptor.md) structure.

### -field ShareDisposition

Indicates whether the described resource can be shared. For a list of valid values, see the **ShareDisposition** member of the [**CM_PARTIAL_RESOURCE_DESCRIPTOR**](./ns-wdm-_cm_partial_resource_descriptor.md) structure.

### -field Spare1

Not used.

### -field Flags

Contains bit flags that are specific to the resource type. The following table shows the flags that are valid if **Type** = **CmResourceTypeInterrupt**:

| Value | Meaning |
|---|---|
| **CM_RESOURCE_INTERRUPT_LEVEL_SENSITIVE** | The IRQ line is level-triggered. (These IRQs are usually sharable.) |
| **CM_RESOURCE_INTERRUPT_LATCHED** | The IRQ line is edge-triggered. |
| **CM_RESOURCE_INTERRUPT_MESSAGE** | If this flag is set, the interrupt is a message-signaled interrupt. Otherwise, the interrupt is a line-based interrupt. |
| **CM_RESOURCE_INTERRUPT_POLICY_INCLUDED** | If this flag is set, the u.Interrupt member includes data that describes the device's interrupt policy. |
| **CM_RESOURCE_INTERRUPT_SECONDARY_INTERRUPT** | The interrupt is capable of waking the operating system from a low-power idle state or a system sleep state. This flag can be set starting with Windows 8. For more information about wake capabilities, see [Enabling Device Wake-Up](/windows-hardware/drivers/kernel/enabling-device-wake-up). |
| **CM_RESOURCE_INTERRUPT_WAKE_HINT** | The interrupt is capable of waking the operating system from a low-power idle state or a system sleep state. This flag can be set starting with Windows 8. For more information about wake capabilities, see [Enabling Device Wake-Up](/windows-hardware/drivers/kernel/enabling-device-wake-up). |

For a list of valid flags for other resource types, see the description of the **Flags** member of the [**CM_PARTIAL_RESOURCE_DESCRIPTOR**](./ns-wdm-_cm_partial_resource_descriptor.md) structure.

### -field Spare2

Not used.

### -field u

Defines the **u** union.

### -field u.Port

Specifies a range of I/O port addresses, using the following members.

Drivers must use [RtlIoDecodeMemIoResource](./nf-wdm-rtliodecodememioresource.md) and [RtlIoEncodeMemIoResource](./nf-wdm-rtlioencodememioresource.md) to read and update this member, rather than updating it directly.

### -field u.Port.Length

The length, in bytes, of the range of assignable I/O port addresses.

### -field u.Port.Alignment

The alignment, in bytes, that the assigned starting address must adhere to. The assigned starting address must be an integer multiple of *Alignment*.

### -field u.Port.MinimumAddress

The minimum bus-relative I/O port address that can be assigned to the device.

### -field u.Port.MaximumAddress

The maximum bus-relative I/O port address that can be assigned to the device.

### -field u.Memory

Specifies a range of memory addresses, using the following members:

Drivers for Windows Vista and later versions of the Windows operating system must use [RtlIoDecodeMemIoResource](./nf-wdm-rtliodecodememioresource.md) and [RtlIoEncodeMemIoResource](./nf-wdm-rtlioencodememioresource.md) to read and update this member, rather than updating it directly.

### -field u.Memory.Length

The length, in bytes, of the range of assignable memory addresses.

### -field u.Memory.Alignment

The alignment, in bytes, that the assigned starting address must adhere to. The assigned starting address must be an integer multiple of *Alignment*.

### -field u.Memory.MinimumAddress

The minimum bus-relative memory address that can be assigned to the device.

### -field u.Memory.MaximumAddress

The maximum bus-relative memory address that can be assigned to the device.

### -field u.Interrupt

Specifies an interrupt vector range, using the following members:

### -field u.Interrupt.MinimumVector

The minimum bus-relative vector that can be assigned to the device.

### -field u.Interrupt.MaximumVector

The maximum bus-relative vector that can be assigned to the device.

If the **CM_RESOURCE_INTERRUPT_MESSAGE** flag bit is set, the values of the **MinimumVector** and **MaximumVector** members have special meanings. For more information, see [Using Interrupt Resource Descriptors](/windows-hardware/drivers/kernel/using-interrupt-resource-descriptors).

The system supplies the following additional members on Windows Vista and later versions of the Windows operating system:

### -field u.Interrupt.Group

Specifies a processor group number. **Group** is a valid but optional member of **u.Interrupt** only in Windows 7 and later versions of Windows. This member exists only if NT_PROCESSOR_GROUPS is defined at compile time. If the **Group** member exists, the **Group** and **TargetedProcessors** members together specify a group affinity that identifies the set of processors that should handle the device's interrupts. To specify an affinity for a particular group, set **AffinityPolicy** to **IrqPolicySpecifiedProcessors** and set **Group** to the appropriate group number. In addition, **TargetedProcessors** must specify the target processors in the group. If you set **AffinityPolicy** to a value other than **IrqPolicySpecifiedProcessors**, set **Group** to ALL_PROCESSOR_GROUPS to indicate that the driver is group-aware (that is, designed to handle information about processor groups). A driver cannot specify target processors if **Group** equals ALL_PROCESSOR_GROUPS; such target specifications are ignored.

### -field u.Interrupt.AffinityPolicy

Specifies an [IRQ_DEVICE_POLICY](./ne-wdm-_irq_device_policy.md) value that indicates how the system should distribute a device's interrupts between processors.

Specifies an [IRQ_DEVICE_POLICY](./ne-wdm-_irq_device_policy.md) value that indicates how the system should distribute a device's interrupts between processors.

### -field u.Interrupt.PriorityPolicy

Specifies an [IRQ_PRIORITY](./ne-wdm-_irq_priority.md) value that indicates the priority with which the system should dispatch the device's interrupts.

### -field u.Interrupt.TargetedProcessors

Specifies a [**KAFFINITY**](/windows-hardware/drivers/kernel/interrupt-affinity-and-priority#about-kaffinity) value that indicates which processors should handle the device's interrupts. This value is used only if **AffinityPolicy** is **IrqPolicySpecifiedProcessors.**

### -field u.Dma

Specifies a DMA setting, using one of the following members:

### -field u.Dma.MinimumChannel

The minimum bus-relative DMA channel that can be assigned to the device.

### -field u.Dma.MaximumChannel

The maximum bus-relative DMA channel that can be assigned to the device.

### -field u.DmaV3

Specifies the DMA settings for a driver that uses version 3 of the [**DMA_OPERATIONS**](./ns-wdm-_dma_operations.md) structure.

The **u.DmaV3** member is available starting with Windows 8.

### -field u.DmaV3.RequestLine

The number of the request line on the system DMA controller that is allocated to the device.

### -field u.DmaV3.Reserved

Not used.

### -field u.DmaV3.Channel

The number of the DMA channel on the system DMA controller that is allocated to the device.

### -field u.DmaV3.TransferWidth

Specifies the width, in bits, of the data bus that the system DMA controller that is allocated to the device uses to transfer data to or from the device.

### -field u.Generic

Not used.

### -field u.Generic.Length

Not used.

### -field u.Generic.Alignment

Not used.

### -field u.Generic.MinimumAddress

Not used.

### -field u.Generic.MaximumAddress

Not used.

### -field u.DevicePrivate

Reserved for system use.

### -field u.DevicePrivate.Data

Reserved for system use.

### -field u.BusNumber

Specifies bus numbers, using the following members:

### -field u.BusNumber.Length

The number of bus numbers required.

### -field u.BusNumber.MinBusNumber

The minimum bus-relative bus number that can be assigned to the device.

### -field u.BusNumber.MaxBusNumber

The maximum bus-relative bus number that can be assigned to the device.

### -field u.BusNumber.Reserved

Not used.

### -field u.ConfigData

Reserved for system use.

### -field u.ConfigData.Priority

Defines the **ULONG** member **Priority**.

### -field u.ConfigData.Reserved1

Not used.

### -field u.ConfigData.Reserved2

Not used.

### -field u.Memory40

Specifies a range of memory addresses, using the following members.

The **u.Memory40** member is available only on Windows Vista and later versions of the Windows operating system. Drivers for these versions of Windows must use [RtlIoDecodeMemIoResource](./nf-wdm-rtliodecodememioresource.md) and [RtlIoEncodeMemIoResource](./nf-wdm-rtlioencodememioresource.md) to read and update this member, rather than updating it directly.

### -field u.Memory40.Length40

The high 32 bits of the 40-bit length, in bytes, of the range of assignable memory addresses. The lower 8 bits are treated as zero.

### -field u.Memory40.Alignment40

The high 32 bits of the 40-bit alignment, in bytes, that the assigned starting address must adhere to. The lower 8 bits are treated as zero. The assigned starting address will be a multiple of the alignment.

### -field u.Memory40.MinimumAddress

The minimum bus-relative memory address that can be assigned to the device.

### -field u.Memory40.MaximumAddress

The maximum bus-relative memory address that can be assigned to the device.

### -field u.Memory48

Specifies a range of memory addresses, using the following members.

The **u.Memory48** member is available only on Windows Vista and later versions of the Windows operating system. Drivers for these versions of Windows must use [RtlIoDecodeMemIoResource](./nf-wdm-rtliodecodememioresource.md) and [RtlIoEncodeMemIoResource](./nf-wdm-rtlioencodememioresource.md) to read and update this member, rather than updating it directly.

### -field u.Memory48.Length48

The high 32 bits of the 48-bit length, in bytes, of the range of assignable memory addresses. The lower 16 bits are treated as zero.

### -field u.Memory48.Alignment48

The high 32 bits of the 48-bit alignment, in bytes, that the assigned starting address must adhere to. The lower 16 bits are treated as zero. The assigned starting address will be a multiple of the alignment.

### -field u.Memory48.MinimumAddress

The minimum bus-relative memory address that can be assigned to the device.

### -field u.Memory48.MaximumAddress

The maximum bus-relative memory address that can be assigned to the device.

### -field u.Memory64

Specifies a range of memory addresses, using the following members.

The **u.Memory64** member is available only on Windows Vista and later versions of the Windows operating system. Drivers for Windows Vista and later versions of the Windows operating system must use [RtlIoDecodeMemIoResource](./nf-wdm-rtliodecodememioresource.md) and [RtlIoEncodeMemIoResource](./nf-wdm-rtlioencodememioresource.md) to read and update this member, rather than updating it directly.

### -field u.Memory64.Length64

The high 32 bits of the 64-bit length, in bytes, of the range of assignable memory addresses. The lower 32 bits are treated as zero.

### -field u.Memory64.Alignment64

The high 32 bits of the 64-bit alignment, in bytes, that the assigned starting address must adhere to. The lower 32 bits are treated as zero. The assigned starting address will be a multiple of the alignment.

### -field u.Memory64.MinimumAddress

The minimum bus-relative memory address that can be assigned to the device.

### -field u.Memory64.MaximumAddress

The maximum bus-relative memory address that can be assigned to the device.

### -field u.Connection

Specifies a connection to a [serial bus](/previous-versions/hh450903(v=vs.85)) or [serial port](/windows-hardware/drivers/serports/), or to a set of one or more [general-purpose I/O](/windows-hardware/drivers/gpio/gpio-driver-support-overview) (GPIO) pins.

The **u.Connection** member is available starting with Windows 8.

The following members describe this connection.

### -field u.Connection.Class

The connection class. This member is set to one of the following values:

| Value | Meaning |
|---|---|
| **CM_RESOURCE_CONNECTION_CLASS_GPIO** | Access the device through one or more pins on a GPIO controller. |
| **CM_RESOURCE_CONNECTION_CLASS_SERIAL** | Access the device through a serial bus or serial port. |

### -field u.Connection.Type

The connection type. If *Class* = CM_RESOURCE_CONNECTION_CLASS_GPIO, *Type* is set to the following value:

| Value | Meaning |
|---|---|
| **CM_RESOURCE_CONNECTION_TYPE_GPIO_IO** | Access the device through GPIO pins that are configured for I/O. |

A GPIO pin that is configured as an interrupt request input is accessed as an ordinary interrupt resource (**CmResourceTypeInterrupt**).

If **Class** = CM_RESOURCE_CONNECTION_CLASS_SERIAL, **Type** is set to one of the following values:

| Value | Meaning |
|---|---|
| **CM_RESOURCE_CONNECTION_TYPE_SERIAL_I2C** | The device is connected to an I2C bus. |
| **CM_RESOURCE_CONNECTION_TYPE_SERIAL_SPI** | The device is connected to an SPI bus. |
| **CM_RESOURCE_CONNECTION_TYPE_SERIAL_UART** | The device is connected to a serial port. |

### -field u.Connection.Reserved1

Not used.

### -field u.Connection.Reserved2

Not used.

### -field u.Connection.IdLowPart

The lower 32 bits of the 64-bit connection ID.

### -field u.Connection.IdHighPart

The upper 32 bits of the 64-bit connection ID.

## -see-also

[**CM_PARTIAL_RESOURCE_DESCRIPTOR**](./ns-wdm-_cm_partial_resource_descriptor.md)

[**IO_RESOURCE_LIST**](./ns-wdm-_io_resource_list.md)

[**IO_RESOURCE_REQUIREMENTS_LIST**](./ns-wdm-_io_resource_requirements_list.md)

[IoConnectInterrupt](./nf-wdm-ioconnectinterrupt.md)