---
UID: NS:wdm._IO_RESOURCE_DESCRIPTOR
title: _IO_RESOURCE_DESCRIPTOR
author: windows-driver-content
description: The IO_RESOURCE_DESCRIPTOR structure describes a range of raw hardware resources, of one type, that can be used by a device. An array of IO_RESOURCE_DESCRIPTOR structures is contained within each IO_RESOURCE_LIST structure.
old-location: kernel\io_resource_descriptor.htm
old-project: kernel
ms.assetid: 03e3a656-c691-4aff-bcc8-4e0bc8390fd7
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _IO_RESOURCE_DESCRIPTOR, *PIO_RESOURCE_DESCRIPTOR, IO_RESOURCE_DESCRIPTOR
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
req.alt-api: IO_RESOURCE_DESCRIPTOR
req.alt-loc: Wdm.h
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
req.typenames: *PIO_RESOURCE_DESCRIPTOR, IO_RESOURCE_DESCRIPTOR
req.product: Windows 10 or later.
---

# _IO_RESOURCE_DESCRIPTOR structure



## -description
The <b>IO_RESOURCE_DESCRIPTOR</b> structure describes a range of raw hardware resources, of one type, that can be used by a device. An array of <b>IO_RESOURCE_DESCRIPTOR</b> structures is contained within each <a href="..\wdm\ns-wdm-_io_resource_list.md">IO_RESOURCE_LIST</a> structure.



## -syntax

````
typedef struct _IO_RESOURCE_DESCRIPTOR {
  UCHAR  Option;
  UCHAR  Type;
  UCHAR  ShareDisposition;
  UCHAR  Spare1;
  USHORT Flags;
  USHORT Spare2;
  union {
    struct {
      ULONG            Length;
      ULONG            Alignment;
      PHYSICAL_ADDRESS MinimumAddress;
      PHYSICAL_ADDRESS MaximumAddress;
    } port;
    struct {
      ULONG            Length;
      ULONG            Alignment;
      PHYSICAL_ADDRESS MinimumAddress;
      PHYSICAL_ADDRESS MaximumAddress;
    } Memory;
    struct {
      ULONG             MinimumVector;
      ULONG             MaximumVector;
#if defined(NT_PROCESSOR_GROUPS)
      IRQ_DEVICE_POLICY AffinityPolicy;
      USHORT            Group;
#else 
      IRQ_DEVICE_POLICY AffinityPolicy;
#endif 
      IRQ_PRIORITY      PriorityPolicy;
      KAFFINITY         TargetedProcessors;
    } Interrupt;
    struct {
      ULONG MinimumChannel;
      ULONG MaximumChannel;
    } Dma;
    struct {
      ULONG RequestLine;
      ULONG Reserved;
      ULONG Channel;
      ULONG TransferWidth;
    } DmaV3;
    struct {
      ULONG            Length;
      ULONG            Alignment;
      PHYSICAL_ADDRESS MinimumAddress;
      PHYSICAL_ADDRESS MaximumAddress;
    } Generic;
    struct {
      ULONG Data[3];
    } DevicePrivate;
    struct {
      ULONG Length;
      ULONG MinBusNumber;
      ULONG MaxBusNumber;
      ULONG Reserved;
    } BusNumber;
    struct {
      ULONG Priority;
      ULONG Reserved1;
      ULONG Reserved2;
    } ConfigData;
    struct {
      ULONG            Length40;
      ULONG            Alignment40;
      PHYSICAL_ADDRESS MinimumAddress;
      PHYSICAL_ADDRESS MaximumAddress;
    } Memory40;
    struct {
      ULONG            Length48;
      ULONG            Alignment48;
      PHYSICAL_ADDRESS MinimumAddress;
      PHYSICAL_ADDRESS MaximumAddress;
    } Memory48;
    struct {
      ULONG            Length64;
      ULONG            Alignment64;
      PHYSICAL_ADDRESS MinimumAddress;
      PHYSICAL_ADDRESS MaximumAddress;
    } Memory64;
    struct {
      UCHAR Class;
      UCHAR Type;
      UCHAR Reserved1;
      UCHAR Reserved2;
      ULONG IdLowPart;
      ULONG IdHighPart;
    } Connection;
  } u;
} IO_RESOURCE_DESCRIPTOR, *PIO_RESOURCE_DESCRIPTOR;
````


## -struct-fields

### -field Option

Specifies whether this resource description is required, preferred, or alternative. One of the following values must be used:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field 0

</td>
<td width="60%">
The specified resource range is required, unless alternative ranges are also specified.

</td>
</tr>
<tr>

### -field IO_RESOURCE_PREFERRED

</td>
<td width="60%">
The specified resource range is preferred to any alternative ranges.

</td>
</tr>
<tr>

### -field IO_RESOURCE_ALTERNATIVE

</td>
<td width="60%">
The specified resource range is an alternative to the range preceding it. For example, if one <b>IO_RESOURCE_DESCRIPTOR</b> structure specifies IRQ 5, with IO_RESOURCE_PREFERRED set, and the next structure specifies IRQ 3, with IO_RESOURCE_ALTERNATIVE set, the PnP manager assigns IRQ 3 to the device only if IRQ 5 is unavailable. (Multiple alternatives can be specified for each resource. Both IO_RESOURCE_ALTERNATIVE and IO_RESOURCE_PREFERRED can be set, indicating a preferred alternative.)

</td>
</tr>
<tr>

### -field IO_RESOURCE_DEFAULT

</td>
<td width="60%">
Not used.

</td>
</tr>
</table>
 


### -field Type

Identifies the resource type. For a list of valid values, see the <b>Type</b> member of the <a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure. 


### -field ShareDisposition

Indicates whether the described resource can be shared. For a list of valid values, see the <b>ShareDisposition</b> member of the <a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure. 


### -field Spare1


### -field Flags

Contains bit flags that are specific to the resource type. The following table shows the flags that are valid if <b>Type</b> = <b>CmResourceTypeInterrupt.</b>

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field CM_RESOURCE_INTERRUPT_LEVEL_SENSITIVE

</td>
<td width="60%">
The IRQ line is level-triggered. (These IRQs are usually sharable.)

</td>
</tr>
<tr>

### -field CM_RESOURCE_INTERRUPT_LATCHED

</td>
<td width="60%">
The IRQ line is edge-triggered.

</td>
</tr>
<tr>

### -field CM_RESOURCE_INTERRUPT_MESSAGE

</td>
<td width="60%">
If this flag is set, the interrupt is a message-signaled interrupt. Otherwise, the interrupt is a line-based interrupt. This flag can be set starting with Windows Vista.

</td>
</tr>
<tr>

### -field CM_RESOURCE_INTERRUPT_POLICY_INCLUDED

</td>
<td width="60%">
If this flag is set, the u.Interrupt member includes data that describes the device's interrupt policy. This flag can be set starting with Windows Vista.

</td>
</tr>
<tr>

### -field CM_RESOURCE_INTERRUPT_SECONDARY_INTERRUPT

</td>
<td width="60%">
The interrupt is a secondary interrupt. This flag can be set starting with Windows 8. For more information about secondary interrupts, see <a href="https://msdn.microsoft.com/0F56AD4C-E0BF-49F1-AB67-0107D08DEF9F">GPIO Interrupts</a>.

</td>
</tr>
<tr>

### -field CM_RESOURCE_INTERRUPT_WAKE_HINT

</td>
<td width="60%">
The interrupt is capable of waking the operating system from a low-power idle state or a system sleep state. This flag can be set starting with Windows 8. For more information about wake capabilities, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544239">Enabling Device Wake-Up</a>.

</td>
</tr>
</table>
 

For a list of valid flags for other resource types, see the description of the <b>Flags</b> member of the <a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure.


### -field Spare2


### -field u


### -field port

Specifies a range of I/O port addresses, using the following members.

Drivers for Windows Vista and later versions of the Windows operating system must use <a href="..\wdm\nf-wdm-rtliodecodememioresource.md">RtlIoDecodeMemIoResource</a> and <a href="..\wdm\nf-wdm-rtlioencodememioresource.md">RtlIoEncodeMemIoResource</a> to read and update this member, rather than updating it directly.


### -field Length

The length, in bytes, of the range of assignable I/O port addresses.


### -field Alignment

The alignment, in bytes, that the assigned starting address must adhere to. The assigned starting address must be an integer multiple of <i>Alignment</i>. 


### -field MinimumAddress

The minimum bus-relative I/O port address that can be assigned to the device.


### -field MaximumAddress

The maximum bus-relative I/O port address that can be assigned to the device.

</dd>
</dl>

### -field Memory

Specifies a range of memory addresses, using the following members:

Drivers for Windows Vista and later versions of the Windows operating system must use <a href="..\wdm\nf-wdm-rtliodecodememioresource.md">RtlIoDecodeMemIoResource</a> and <a href="..\wdm\nf-wdm-rtlioencodememioresource.md">RtlIoEncodeMemIoResource</a> to read and update this member, rather than updating it directly.


### -field Length

The length, in bytes, of the range of assignable memory addresses.


### -field Alignment

The alignment, in bytes, that the assigned starting address must adhere to. The assigned starting address must be an integer multiple of <i>Alignment</i>.


### -field MinimumAddress

The minimum bus-relative memory address that can be assigned to the device.


### -field MaximumAddress

The maximum bus-relative memory address that can be assigned to the device.

</dd>
</dl>

### -field Interrupt

Specifies an interrupt vector range, using the following members:


### -field MinimumVector

The minimum bus-relative vector that can be assigned to the device.


### -field MaximumVector

The maximum bus-relative vector that can be assigned to the device.

If the <b>CM_RESOURCE_INTERRUPT_MESSAGE</b> flag bit is set, the values of the <b>MinimumVector</b> and <b>MaximumVector</b> members have special meanings. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565394">Using Interrupt Resource Descriptors</a>.


The system supplies the following additional members on Windows Vista and later versions of the Windows operating system:


### -field AffinityPolicy

Specifies an <a href="..\wdm\ne-wdm-_irq_device_policy.md">IRQ_DEVICE_POLICY</a> value that indicates how the system should distribute a device's interrupts between processors.


### -field Group

Specifies a processor group number. <b>Group</b> is a valid (but optional) member of <b>u.Interrupt</b> only in Windows 7 and later versions of Windows. This member exists only if NT_PROCESSOR_GROUPS is defined at compile time. If the <b>Group</b> member exists, the <b>Group</b> and <b>TargetedProcessors</b> members together specify a group affinity that identifies the set of processors that should handle the device's interrupts. To specify an affinity for a particular group, set <b>AffinityPolicy</b> to <b>IrqPolicySpecifiedProcessors</b> and set <b>Group</b> to the appropriate group number. In addition, <b>TargetedProcessors</b> must specify the target processors in the group. If you set <b>AffinityPolicy</b> to a value other than <b>IrqPolicySpecifiedProcessors</b>, set <b>Group</b> to ALL_PROCESSOR_GROUPS to indicate that the driver is group-aware (that is, designed to handle information about processor groups). A driver cannot specify target processors if <b>Group</b> equals ALL_PROCESSOR_GROUPS; such target specifications are ignored.


### -field AffinityPolicy

Specifies an <a href="..\wdm\ne-wdm-_irq_device_policy.md">IRQ_DEVICE_POLICY</a> value that indicates how the system should distribute a device's interrupts between processors.


### -field PriorityPolicy

Specifies an <a href="..\wdm\ne-wdm-_irq_priority.md">IRQ_PRIORITY</a> value that indicates the priority with which the system should dispatch the device's interrupts.


### -field TargetedProcessors

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a> value that indicates which processors should handle the device's interrupts. This value is used only if <b>AffinityPolicy</b> is <b>IrqPolicySpecifiedProcessors.</b>

</dd>
</dl>

### -field Dma

Specifies a DMA setting, using one of the following members:


### -field MinimumChannel

The minimum bus-relative DMA channel that can be assigned to the device.


### -field MaximumChannel

The maximum bus-relative DMA channel that can be assigned to the device.

</dd>
</dl>

### -field DmaV3

Specifies the DMA settings for a driver that uses version 3 of the <a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a> structure.

The <b>u.DmaV3</b> member is available starting with Windows 8.


### -field RequestLine

The number of the request line on the system DMA controller that is allocated to the device.


### -field Reserved

Not used.


### -field Channel

The number of the DMA channel on the system DMA controller that is allocated to the device.


### -field TransferWidth

Specifies the width, in bits, of the data bus that the system DMA controller that is allocated to the device uses to transfer data to or from the device.

</dd>
</dl>

### -field Generic

Not used.


### -field DevicePrivate

Reserved for system use. 


### -field BusNumber

Specifies bus numbers, using the following members:


### -field Length

The number of bus numbers required.


### -field MinBusNumber

The minimum bus-relative bus number that can be assigned to the device.


### -field MaxBusNumber

The maximum bus-relative bus number that can be assigned to the device.


### -field Reserved

Not used.

</dd>
</dl>

### -field ConfigData

Reserved for system use. 


### -field Memory40

Specifies a range of memory addresses, using the following members.

The <b>u.Memory40</b> member is available only on Windows Vista and later versions of the Windows operating system. Drivers for these versions of Windows must use <a href="..\wdm\nf-wdm-rtliodecodememioresource.md">RtlIoDecodeMemIoResource</a> and <a href="..\wdm\nf-wdm-rtlioencodememioresource.md">RtlIoEncodeMemIoResource</a> to read and update this member, rather than updating it directly.


### -field Length40

The high 32 bits of the 40-bit length, in bytes, of the range of assignable memory addresses. The lower 8 bits are treated as zero.


### -field Alignment40

The high 32 bits of the 40-bit alignment, in bytes, that the assigned starting address must adhere to. The lower 8 bits are treated as zero. The assigned starting address will be a multiple of the alignment.


### -field MinimumAddress

The minimum bus-relative memory address that can be assigned to the device.


### -field MaximumAddress

The maximum bus-relative memory address that can be assigned to the device.

</dd>
</dl>

### -field Memory48

Specifies a range of memory addresses, using the following members.

The <b>u.Memory48</b> member is available only on Windows Vista and later versions of the Windows operating system. Drivers for these versions of Windows must use <a href="..\wdm\nf-wdm-rtliodecodememioresource.md">RtlIoDecodeMemIoResource</a> and <a href="..\wdm\nf-wdm-rtlioencodememioresource.md">RtlIoEncodeMemIoResource</a> to read and update this member, rather than updating it directly.


### -field Length48

The high 32 bits of the 48-bit length, in bytes, of the range of assignable memory addresses. The lower 16 bits are treated as zero.


### -field Alignment48

The high 32 bits of the 48-bit alignment, in bytes, that the assigned starting address must adhere to. The lower 16 bits are treated as zero. The assigned starting address will be a multiple of the alignment.


### -field MinimumAddress

The minimum bus-relative memory address that can be assigned to the device.


### -field MaximumAddress

The maximum bus-relative memory address that can be assigned to the device.

</dd>
</dl>

### -field Memory64

Specifies a range of memory addresses, using the following members.

The <b>u.Memory64</b> member is available only on Windows Vista and later versions of the Windows operating system. Drivers for Windows Vista and later versions of the Windows operating system must use <a href="..\wdm\nf-wdm-rtliodecodememioresource.md">RtlIoDecodeMemIoResource</a> and <a href="..\wdm\nf-wdm-rtlioencodememioresource.md">RtlIoEncodeMemIoResource</a> to read and update this member, rather than updating it directly.


### -field Length64

The high 32 bits of the 64-bit length, in bytes, of the range of assignable memory addresses. The lower 32 bits are treated as zero.


### -field Alignment64

The high 32 bits of the 64-bit alignment, in bytes, that the assigned starting address must adhere to. The lower 32 bits are treated as zero. The assigned starting address will be a multiple of the alignment.


### -field MinimumAddress

The minimum bus-relative memory address that can be assigned to the device.


### -field MaximumAddress

The maximum bus-relative memory address that can be assigned to the device.

</dd>
</dl>

### -field Connection

Specifies a connection to a <a href="https://msdn.microsoft.com/2c660e14-5b27-4610-a328-735b07ed0773">serial bus</a> or <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/">serial port</a>, or to a set of one or more <a href="https://msdn.microsoft.com/450E7F80-D9AC-4F52-8062-2DA5343C8D0F">general-purpose I/O</a> (GPIO) pins. 

The <b>u.Connection</b> member is available starting with Windows 8.

The following members describe this connection.


### -field Class

The connection class. This member is set to one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field CM_RESOURCE_CONNECTION_CLASS_GPIO

</td>
<td width="60%">
Access the device through one or more pins on a GPIO controller.

</td>
</tr>
<tr>

### -field CM_RESOURCE_CONNECTION_CLASS_SERIAL

</td>
<td width="60%">
Access the device through a serial bus or serial port.

</td>
</tr>
</table>
 


### -field Type

The connection type. If <i>Class</i> = CM_RESOURCE_CONNECTION_CLASS_GPIO, <i>Type</i> is set to the following value:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field CM_RESOURCE_CONNECTION_TYPE_GPIO_IO

</td>
<td width="60%">
Access the device through GPIO pins that are configured for I/O.

</td>
</tr>
</table>
 

<div class="alert"><b>Note</b>  A GPIO pin that is configured as an interrupt request input is accessed as an ordinary interrupt resource (<b>CmResourceTypeInterrupt</b>).</div>
<div> </div>
If <b>Class</b> = CM_RESOURCE_CONNECTION_CLASS_SERIAL, <b>Type</b> is set to one of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field CM_RESOURCE_CONNECTION_TYPE_SERIAL_I2C

</td>
<td width="60%">
The device is connected to an I²C bus.

</td>
</tr>
<tr>

### -field CM_RESOURCE_CONNECTION_TYPE_SERIAL_SPI

</td>
<td width="60%">
The device is connected to an SPI bus.

</td>
</tr>
<tr>

### -field CM_RESOURCE_CONNECTION_TYPE_SERIAL_UART

</td>
<td width="60%">
The device is connected to a serial port.

</td>
</tr>
</table>
 


### -field Reserved1

Not used. 


### -field Reserved2

Not used. 


### -field IdLowPart

The lower 32 bits of the 64-bit connection ID.


### -field IdHighPart

The upper 32 bits of the 64-bit connection ID.

</dd>
</dl>
</dd>
</dl>

## -remarks


## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_io_resource_requirements_list.md">IO_RESOURCE_REQUIREMENTS_LIST</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_io_resource_list.md">IO_RESOURCE_LIST</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-ioconnectinterrupt.md">IoConnectInterrupt</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IO_RESOURCE_DESCRIPTOR structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

