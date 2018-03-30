---
UID: NS:wdm._CM_PARTIAL_RESOURCE_DESCRIPTOR
title: "_CM_PARTIAL_RESOURCE_DESCRIPTOR"
author: windows-driver-content
description: The CM_PARTIAL_RESOURCE_DESCRIPTOR structure specifies one or more system hardware resources, of a single type, assigned to a device.
old-location: kernel\cm_partial_resource_descriptor.htm
old-project: kernel
ms.assetid: 96bf7bab-b8f5-439c-8717-ea6956ed0213
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PCM_PARTIAL_RESOURCE_DESCRIPTOR, CM_PARTIAL_RESOURCE_DESCRIPTOR, CM_PARTIAL_RESOURCE_DESCRIPTOR structure [Kernel-Mode Driver Architecture], CM_RESOURCE_CONNECTION_CLASS_GPIO, CM_RESOURCE_CONNECTION_CLASS_SERIAL, CM_RESOURCE_CONNECTION_TYPE_GPIO_IO, CM_RESOURCE_CONNECTION_TYPE_SERIAL_I2C, CM_RESOURCE_CONNECTION_TYPE_SERIAL_SPI, CM_RESOURCE_CONNECTION_TYPE_SERIAL_UART, CmResourceShareDeviceExclusive, CmResourceShareDriverExclusive, CmResourceShareShared, PCM_PARTIAL_RESOURCE_DESCRIPTOR, PCM_PARTIAL_RESOURCE_DESCRIPTOR structure pointer [Kernel-Mode Driver Architecture], _CM_PARTIAL_RESOURCE_DESCRIPTOR, kernel.cm_partial_resource_descriptor, kstruct_a_2a821975-e3b8-4ce0-9dd5-8afe348001d8.xml, wdm/CM_PARTIAL_RESOURCE_DESCRIPTOR, wdm/PCM_PARTIAL_RESOURCE_DESCRIPTOR"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	CM_PARTIAL_RESOURCE_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: CM_PARTIAL_RESOURCE_DESCRIPTOR, *PCM_PARTIAL_RESOURCE_DESCRIPTOR
req.product: Windows 10 or later.
---

# _CM_PARTIAL_RESOURCE_DESCRIPTOR structure


## -description


The <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b> structure specifies one or more system hardware resources, of a single type, assigned to a device. This structure is used to create an array within a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541981">CM_PARTIAL_RESOURCE_LIST</a> structure.
   
  


## -struct-fields




### -field Type

Identifies the resource type. The constant value specified for <b>Type</b> indicates which structure within the <b>u</b> union is valid, as indicated in the following table. (These flags are used within both <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b> and <a href="https://msdn.microsoft.com/03e3a656-c691-4aff-bcc8-4e0bc8390fd7">IO_RESOURCE_DESCRIPTOR</a> structures, except where noted.)

<table>
<tr>
<th>Type value</th>
<th>u member substructure</th>
</tr>
<tr>
<td>
<b>CmResourceTypePort</b>

</td>
<td>
<b>u.Port</b>

</td>
</tr>
<tr>
<td>
<b>CmResourceTypeInterrupt</b>

</td>
<td><b>u.Interrupt</b> or <b>u.MessageInterrupt</b>.If the CM_RESOURCE_INTERRUPT_MESSAGE flag of <b>Flags</b> is set, use <b>u.MessageInterrupt</b>; otherwise, use <b>u.Interrupt</b>.

</td>
</tr>
<tr>
<td>
<b>CmResourceTypeMemory</b>

</td>
<td>
<b>u.Memory</b>

</td>
</tr>
<tr>
<td>
<b>CmResourceTypeMemoryLarge</b>

</td>
<td>One of <b>u.Memory40</b>, <b>u.Memory48</b>, or <b>u.Memory64</b>.The CM_RESOURCE_MEMORY_LARGE_<i>XXX</i> flags set in the <b>Flags</b> member determines which structure is used.

</td>
</tr>
<tr>
<td>
<b>CmResourceTypeDma</b>

</td>
<td>
<b>u.Dma</b>
          (if CM_RESOURCE_DMA_V3 is not set) or <b>u.DmaV3</b> (if CM_RESOURCE_DMA_V3 flag is set)

</td>
</tr>
<tr>
<td>
<b>CmResourceTypeDevicePrivate</b>

</td>
<td>
<b>u.DevicePrivate</b>

</td>
</tr>
<tr>
<td>
<b>CmResourceTypeBusNumber</b>

</td>
<td>
<b>u.BusNumber</b>

</td>
</tr>
<tr>
<td>
<b>CmResourceTypeDeviceSpecific</b>

</td>
<td><b>u.DeviceSpecificData</b>(Not used within <b>IO_RESOURCE_DESCRIPTOR</b>.)

</td>
</tr>
<tr>
<td>
<b>CmResourceTypePcCardConfig</b>

</td>
<td>
<b>u.DevicePrivate</b>

</td>
</tr>
<tr>
<td>
<b>CmResourceTypeMfCardConfig</b>

</td>
<td>
<b>u.DevicePrivate</b>

</td>
</tr>
<tr>
<td>
<b>CmResourceTypeConnection</b>

</td>
<td>
<b>u.Connection</b>

</td>
</tr>
<tr>
<td>
<b>CmResourceTypeConfigData</b>

</td>
<td>
<i>Reserved for system use.</i>

</td>
</tr>
<tr>
<td>
<b>CmResourceTypeNonArbitrated</b>

</td>
<td>
<i>
           Not used.</i>

</td>
</tr>
</table>
 


### -field ShareDisposition

Indicates whether the described resource can be shared. Valid constant values are listed in the following table.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="CmResourceShareDeviceExclusive"></a><a id="cmresourcesharedeviceexclusive"></a><a id="CMRESOURCESHAREDEVICEEXCLUSIVE"></a><dl>
<dt><b>CmResourceShareDeviceExclusive</b></dt>
</dl>
</td>
<td width="60%">
The device requires exclusive use of the resource.

</td>
</tr>
<tr>
<td width="40%"><a id="CmResourceShareDriverExclusive"></a><a id="cmresourcesharedriverexclusive"></a><a id="CMRESOURCESHAREDRIVEREXCLUSIVE"></a><dl>
<dt><b>CmResourceShareDriverExclusive</b></dt>
</dl>
</td>
<td width="60%">
The driver requires exclusive use of the resource. (Not supported for WDM drivers.)

</td>
</tr>
<tr>
<td width="40%"><a id="CmResourceShareShared"></a><a id="cmresourceshareshared"></a><a id="CMRESOURCESHARESHARED"></a><dl>
<dt><b>CmResourceShareShared</b></dt>
</dl>
</td>
<td width="60%">
The resource can be shared without restriction.

</td>
</tr>
</table>
 


### -field Flags

Contains flag bits that are specific to the resource type, as indicated in the following table. Flags can be bitwise-ORed together as appropriate.

<table>
<tr>
<th>Resource type</th>
<th colspan="2">Flag</th>
<th>Definition</th>
</tr>
<tr>
<td colspan="4">
<b>CmResourceTypePort</b>

</td>
</tr>
<tr>
<td></td>
<td colspan="2">
CM_RESOURCE_PORT_MEMORY

</td>
<td>
The device is accessed in memory address space.

</td>
</tr>
<tr>
<td></td>
<td colspan="2">
CM_RESOURCE_PORT_IO

</td>
<td>
The device is accessed in I/O address space.

</td>
</tr>
<tr>
<td></td>
<td colspan="2">
CM_RESOURCE_PORT_10_BIT_DECODE

</td>
<td>
The device decodes 10 bits of the port address.

</td>
</tr>
<tr>
<td></td>
<td colspan="2">
CM_RESOURCE_PORT_12_BIT_DECODE

</td>
<td>
The device decodes 12 bits of the port address.

</td>
</tr>
<tr>
<td></td>
<td colspan="2">
CM_RESOURCE_PORT_16_BIT_DECODE

</td>
<td>
The device decodes 16 bits of the port address.

</td>
</tr>
<tr>
<td></td>
<td colspan="2">
CM_RESOURCE_PORT_POSITIVE_DECODE

</td>
<td>
The device uses "positive decode" instead of "subtractive decode". (In general, PCI devices use positive decode and ISA buses use subtractive decode.)

</td>
</tr>
<tr>
<td></td>
<td colspan="2">
CM_RESOURCE_PORT_PASSIVE_DECODE

</td>
<td>
The device decodes the port but the driver does not use it.

</td>
</tr>
<tr>
<td></td>
<td colspan="2">
CM_RESOURCE_PORT_WINDOW_DECODE

</td>
<td>
<u>Reserved for system use.
          </u>

</td>
</tr>
<tr>
<td colspan="4">
<b>CmResourceTypeInterrupt</b>

</td>
</tr>
<tr>
<td></td>
<td colspan="2">
CM_RESOURCE_INTERRUPT_LEVEL_SENSITIVE

</td>
<td>
The IRQ line is level-triggered. (These IRQs are usually sharable.)

</td>
</tr>
<tr>
<td></td>
<td colspan="2">
CM_RESOURCE_INTERRUPT_LATCHED

</td>
<td>
The IRQ line is edge-triggered.

</td>
</tr>
<tr>
<td></td>
<td colspan="2">
CM_RESOURCE_INTERRUPT_MESSAGE

</td>
<td>
If this flag is set, the interrupt is a message-signaled interrupt. Otherwise, the interrupt is a line-based interrupt. This flag can be set starting with Windows Vista.

</td>
</tr>
<tr>
<td></td>
<td colspan="2">
CM_RESOURCE_INTERRUPT_POLICY_INCLUDED

</td>
<td>
Not used with the <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b> structure. For more information about this flag, see <a href="https://msdn.microsoft.com/03e3a656-c691-4aff-bcc8-4e0bc8390fd7">IO_RESOURCE_DESCRIPTOR</a>.

</td>
</tr>
<tr>
<td></td>
<td colspan="2">
CM_RESOURCE_INTERRUPT_SECONDARY_INTERRUPT

</td>
<td>
The interrupt is a secondary interrupt. This flag can be set starting with Windows 8. For more information about secondary interrupts, see <a href="https://msdn.microsoft.com/0F56AD4C-E0BF-49F1-AB67-0107D08DEF9F">GPIO Interrupts</a>.

</td>
</tr>
<tr>
<td></td>
<td colspan="2">
CM_RESOURCE_INTERRUPT_WAKE_HINT

</td>
<td>
The interrupt is capable of waking the operating system from a low-power idle state or a system sleep state. This flag can be set starting with Windows 8. For more information about wake capabilities, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544239">Enabling Device Wake-Up</a>.

</td>
</tr>
<tr>
<td colspan="4">
<b>CmResourceTypeMemory</b>

</td>
</tr>
<tr>
<td></td>
<td colspan="2">
CM_RESOURCE_MEMORY_READ_WRITE

</td>
<td>
The memory range is readable and writable.

</td>
</tr>
<tr>
<td></td>
<td colspan="2">
CM_RESOURCE_MEMORY_READ_ONLY

</td>
<td>
The memory range is read-only.

</td>
</tr>
<tr>
<td></td>
<td colspan="2">
CM_RESOURCE_MEMORY_WRITE_ONLY

</td>
<td>
The memory range is write-only.

</td>
</tr>
<tr>
<td></td>
<td colspan="2">
CM_RESOURCE_MEMORY_PREFETCHABLE

</td>
<td>
The memory range is prefetchable.

</td>
</tr>
<tr>
<td></td>
<td colspan="2">
CM_RESOURCE_MEMORY_COMBINEDWRITE

</td>
<td>
Combined-write caching is allowed.

</td>
</tr>
<tr>
<td></td>
<td colspan="2">
CM_RESOURCE_MEMORY_24

</td>
<td>
The device uses 24-bit addressing.

</td>
</tr>
<tr>
<td></td>
<td colspan="2">
CM_RESOURCE_MEMORY_CACHEABLE

</td>
<td>
The memory range is cacheable.

</td>
</tr>
<tr>
<td colspan="4">
<b>CmResourceTypeMemoryLarge</b>

</td>
</tr>
<tr>
<td></td>
<td>
CM_RESOURCE_MEMORY_LARGE_40

</td>
<td colspan="2">
The memory descriptor uses the <b>u.Memory40</b> member.

</td>
</tr>
<tr>
<td></td>
<td>
CM_RESOURCE_MEMORY_LARGE_48

</td>
<td colspan="2">
The memory descriptor uses the <b>u.Memory48</b> member.

</td>
</tr>
<tr>
<td></td>
<td>
CM_RESOURCE_MEMORY_LARGE_64

</td>
<td colspan="2">
The memory descriptor uses the <b>u.Memory64</b> member.

</td>
</tr>
<tr>
<td colspan="4">
<b>CmResourceTypeDma</b>

</td>
</tr>
<tr>
<td></td>
<td colspan="2">
CM_RESOURCE_DMA_8

</td>
<td>
8-bit DMA channel

</td>
</tr>
<tr>
<td></td>
<td colspan="2">
CM_RESOURCE_DMA_16

</td>
<td>
16-bit DMA channel

</td>
</tr>
<tr>
<td></td>
<td colspan="2">
CM_RESOURCE_DMA_32

</td>
<td>
32-bit DMA channel

</td>
</tr>
<tr>
<td></td>
<td colspan="2">
CM_RESOURCE_DMA_8_AND_16

</td>
<td>
8-bit and 16-bit DMA channel

</td>
</tr>
<tr>
<td></td>
<td colspan="2">
CM_RESOURCE_DMA_BUS_MASTER

</td>
<td>
The device supports bus master DMA transfers.

</td>
</tr>
<tr>
<td></td>
<td colspan="2">
CM_RESOURCE_DMA_TYPE_A

</td>
<td>
Type A DMA

</td>
</tr>
<tr>
<td></td>
<td colspan="2">
CM_RESOURCE_DMA_TYPE_B

</td>
<td>
Type B DMA

</td>
</tr>
<tr>
<td></td>
<td colspan="2">
CM_RESOURCE_DMA_TYPE_F

</td>
<td>
Type F DMA

</td>
</tr>
<tr>
<td></td>
<td colspan="2">
CM_RESOURCE_DMA_V3

</td>
<td>
Use the <b>DmaV3</b> member instead of the <b>Dma</b> member. The <b>DmaV3</b> member is available starting with Windows 8.

</td>
</tr>
</table>
 


### -field u


### -field u.Generic

Not used.


### -field u.Generic.Start

 


### -field u.Generic.Length

 


### -field u.Port

Specifies a range of I/O port addresses, using the following members.

Drivers for Windows Vista and later versions of the Windows operating system can use <a href="https://msdn.microsoft.com/library/windows/hardware/ff561768">RtlCmDecodeMemIoResource</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff561774">RtlCmEncodeMemIoResource</a> to read and update the <b>u.Port</b> member, rather than updating it directly.


### -field u.Port.Start

For raw resources: Specifies the bus-relative physical address of the lowest of a range of contiguous I/O port addresses allocated to the device.

For translated resources: Specifies the system physical address of the lowest of a range of contiguous I/O port addresses allocated to the device.

For more information about raw and translated resources, see Remarks.


### -field u.Port.Length

The length, in bytes, of the range of allocated I/O port addresses.


### -field u.Interrupt

Specifies an interrupt vector and level, using the following members:


### -field u.Interrupt.Group

Specifies the processor group number. This member exists only if the NT_PROCESSOR_GROUPS constant is defined at compile time. This member can be nonzero only on Windows 7 and later versions of Windows. The <b>Group</b> and <b>Affinity</b> members together specify a group affinity that indicates which processors the device can interrupt. To specify an affinity for any group, set <b>Group</b> to ALL_PROCESSOR_GROUPS.


### -field u.Interrupt.Level

For raw resources: Specifies the device's bus-specific IRQL (if appropriate for the platform and bus).

For translated resources: Specifies the DIRQL assigned to the device.

For more information about raw and translated resources, see Remarks.


### -field u.Interrupt.Vector

For raw resources: Specifies the device's bus-specific interrupt vector (if appropriate for the platform and bus).

For translated resources: Specifies the global system interrupt vector assigned to the device.

For more information about raw and translated resources, see Remarks.


### -field u.Interrupt.Affinity

Contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a>-typed bitmask value indicating the set of processors the device can interrupt. To indicate that the device can interrupt any processor, this member is set to -1.


### -field u.MessageInterrupt

Specifies a message-signaled interrupt. This member is a union. Use <b>u.MessageInterrupt.Raw</b> for raw resources, and <b>u.MessageInterrupt.Translated</b> for translated resources. This type of resource is only returned on Windows Vista and later versions of the Windows operating system.

For more information about raw and translated resources, see Remarks.

The <b>u.MessageInterrupt.Raw</b> member has the following members:


### -field u.MessageInterrupt.DUMMYUNIONNAME

 


### -field u.MessageInterrupt.DUMMYUNIONNAME.Raw


### -field u.MessageInterrupt.DUMMYUNIONNAME.Raw.Group

Specifies a processor group number. This member exists only if NT_PROCESSOR_GROUPS is defined at compile time. This member can be nonzero only on Windows 7 and later versions of Windows. The <b>Group</b> and <b>Affinity</b> members together specify a group affinity that indicates which processors can receive the device's interrupts. To specify an affinity for any group, set <b>Group</b> to ALL_PROCESSOR_GROUPS.


### -field u.MessageInterrupt.DUMMYUNIONNAME.Raw.Reserved

Not used.


### -field u.MessageInterrupt.DUMMYUNIONNAME.Raw.MessageCount

Specifies the number of message-signaled interrupts generated for this driver.


### -field u.MessageInterrupt.DUMMYUNIONNAME.Raw.Vector

Specifies the device's interrupt vector.


### -field u.MessageInterrupt.DUMMYUNIONNAME.Raw.Affinity

Specifies a KAFFINITY value that indicates the processors that receive the device's interrupts.


### -field u.MessageInterrupt.DUMMYUNIONNAME.Translated

The <b>u.MessageInterrupt.Translated</b> member has the following members:


### -field u.MessageInterrupt.DUMMYUNIONNAME.Translated.Group

Specifies a processor group number. This member exists only if NT_PROCESSOR_GROUPS is defined at compile time. This member can be nonzero only on Windows 7 and later versions of Windows. The <b>Translated.Group</b> and <b>Translated.Affinity</b> members together specify a group affinity that indicates which processors can receive the device's interrupts. To specify an affinity for any group, set <b>Translated.Group</b> to ALL_PROCESSOR_GROUPS.


### -field u.MessageInterrupt.DUMMYUNIONNAME.Translated.Level

Specifies the device IRQL (DIRQL) assigned to the device's interrupts.

Specifies the device IRQL (DIRQL) assigned to the device's interrupts.


### -field u.MessageInterrupt.DUMMYUNIONNAME.Translated.Vector

Specifies the device's interrupt vector.


### -field u.MessageInterrupt.DUMMYUNIONNAME.Translated.Affinity

Specifies a KAFFINITY value that identifies the processors that receive the device's interrupts.


### -field u.Memory

Specifies a range of memory addresses, using the following members.

Drivers for Windows Vista and later versions of the Windows operating system can use <a href="https://msdn.microsoft.com/library/windows/hardware/ff561768">RtlCmDecodeMemIoResource</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff561774">RtlCmEncodeMemIoResource</a> to read and update the <b>u.Memory</b> member, rather than updating it directly.


### -field u.Memory.Start

For raw resources: Specifies the bus-relative physical address of the lowest of a range of contiguous memory addresses allocated to the device.

For translated resources: Specifies the system physical address of the lowest of a range of contiguous memory addresses allocated to the device.

For more information about raw and translated resources, see Remarks.


### -field u.Memory.Length

Specifies the length, in bytes, of the range of allocated memory addresses.


### -field u.Dma

Specifies a DMA setting, using one of the following members:


### -field u.Dma.Channel

Specifies the number of the DMA channel on a system DMA controller that the device can use.


### -field u.Dma.Port

Specifies the number of the DMA port that an MCA-type device can use.


### -field u.Dma.Reserved1

Not used.


### -field u.DmaV3

Specifies the DMA settings for a driver that uses version 3 of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a> structure.

The <b>u.DmaV3</b> member is available starting with Windows 8.


### -field u.DmaV3.Channel

Specifies the number of the DMA channel on the system DMA controller that is allocated to the device.


### -field u.DmaV3.RequestLine

Specifies the number of the request line on the system DMA controller that is allocated to the device.


### -field u.DmaV3.TransferWidth

Specifies the width, in bits, of the data bus that the system DMA controller that is allocated to the device uses to transfer data to or from the device.


### -field u.DmaV3.Reserved1

Not used.


### -field u.DmaV3.Reserved2

Not used.


### -field u.DmaV3.Reserved3

Not used.


### -field u.DevicePrivate

Reserved for system use.


### -field u.DevicePrivate.Data

 


### -field u.BusNumber

Specifies bus numbers, using the following members:


### -field u.BusNumber.Start

Specifies the lowest-numbered of a range of contiguous buses allocated to the device.


### -field u.BusNumber.Length

Specifies the number of buses allocated to the device.


### -field u.BusNumber.Reserved

Not used.


### -field u.DeviceSpecificData

Specifies the size of a device-specific, private structure that is appended to the end of the <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b> structure. If <b>u.DeviceSpecificData</b> is used, the <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b> structure must be the last one in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541981">CM_PARTIAL_RESOURCE_LIST</a> array.

Examples of device-specific structures include <a href="https://msdn.microsoft.com/library/windows/hardware/ff541947">CM_FLOPPY_DEVICE_DATA</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff541967">CM_KEYBOARD_DEVICE_DATA</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff541998">CM_SCSI_DEVICE_DATA</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff542003">CM_SERIAL_DEVICE_DATA</a>.


### -field u.DeviceSpecificData.DataSize

Specifies the number of bytes appended to the end of the <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b> structure.


### -field u.DeviceSpecificData.Reserved1

Not used.


### -field u.DeviceSpecificData.Reserved2

Not used.


### -field u.Memory40

Specifies a range of memory addresses, using the following members.

The <b>u.Memory40</b> member is available only on Windows Vista and later versions of the Windows operating system. Drivers must use <a href="https://msdn.microsoft.com/library/windows/hardware/ff561768">RtlCmDecodeMemIoResource</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff561774">RtlCmEncodeMemIoResource</a> to read and update this member, rather than updating it directly.


### -field u.Memory40.Start

For raw resources: Specifies the bus-relative physical address of the lowest of a range of contiguous memory addresses that are allocated to the device.

For translated resources: Specifies the system physical address of the lowest of a range of contiguous memory addresses that are allocated to the device.

For more information about raw and translated resources, see Remarks.


### -field u.Memory40.Length40

Contains the high 32 bits of the 40-bit length, in bytes, of the range of allocated memory addresses. The lowest 8 bits are treated as zero.


### -field u.Memory48

Specifies a range of memory addresses, using the following members.

The <b>u.Memory48</b> member is available only on Windows Vista and later versions of the Windows operating system. Drivers must use <a href="https://msdn.microsoft.com/library/windows/hardware/ff561768">RtlCmDecodeMemIoResource</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff561774">RtlCmEncodeMemIoResource</a> to read and update this member, rather than updating it directly.


### -field u.Memory48.Start

For raw resources: Specifies the bus-relative physical address of the lowest of a range of contiguous memory addresses that are allocated to the device.

For translated resources: Specifies the system physical address of the lowest of a range of contiguous memory addresses that are allocated to the device.

For more information about raw and translated resources, see Remarks.


### -field u.Memory48.Length48

Contains the high 32 bits of the 48-bit length, in bytes, of the range of allocated memory addresses. The lowest 16 bits are treated as zero.


### -field u.Memory64

Specifies a range of memory addresses, using the following members.

The <b>u.Memory64</b> member is available only on Windows Vista and later versions of the Windows operating system. Drivers must use <a href="https://msdn.microsoft.com/library/windows/hardware/ff561768">RtlCmDecodeMemIoResource</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff561774">RtlCmEncodeMemIoResource</a> to read and update this member, rather than updating it directly.


### -field u.Memory64.Start

For raw resources: Specifies the bus-relative physical address of the lowest of a range of contiguous memory addresses that are allocated to the device.

For translated resources: Specifies the system physical address of the lowest of a range of contiguous memory addresses that are allocated to the device.

For more information about raw and translated resources, see Remarks.


### -field u.Memory64.Length64

Contains the high 32 bits of the 64-bit length, in bytes, of the range of allocated memory addresses. The lowest 32 bits are treated as zero.


### -field u.Connection

Specifies a connection to a <a href="https://msdn.microsoft.com/2c660e14-5b27-4610-a328-735b07ed0773">serial bus</a> or <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/">serial port</a>, or to a set of one or more <a href="https://msdn.microsoft.com/450E7F80-D9AC-4F52-8062-2DA5343C8D0F">general-purpose I/O</a> (GPIO) pins. The following members describe this connection.

The <b>u.Connection</b> member is available starting with Windows 8.


### -field u.Connection.Class

Specifies the connection class. This member is set to one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="CM_RESOURCE_CONNECTION_CLASS_GPIO"></a><a id="cm_resource_connection_class_gpio"></a><dl>
<dt><b>CM_RESOURCE_CONNECTION_CLASS_GPIO</b></dt>
</dl>
</td>
<td width="60%">
Access the device through one or more pins on a GPIO controller.

</td>
</tr>
<tr>
<td width="40%"><a id="CM_RESOURCE_CONNECTION_CLASS_SERIAL"></a><a id="cm_resource_connection_class_serial"></a><dl>
<dt><b>CM_RESOURCE_CONNECTION_CLASS_SERIAL</b></dt>
</dl>
</td>
<td width="60%">
Access the device through a serial bus or serial port.

</td>
</tr>
</table>
 


### -field u.Connection.Type

Specifies the connection type.

If <b>Class</b> = CM_RESOURCE_CONNECTION_CLASS_GPIO, <b>Type</b> is set to the following value.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="CM_RESOURCE_CONNECTION_TYPE_GPIO_IO"></a><a id="cm_resource_connection_type_gpio_io"></a><dl>
<dt><b>CM_RESOURCE_CONNECTION_TYPE_GPIO_IO</b></dt>
</dl>
</td>
<td width="60%">
Access the device through GPIO pins that are configured for I/O.

</td>
</tr>
</table>
 

<div class="alert"><b>Note</b>  A GPIO pin that is configured as an interrupt request input is accessed as an ordinary interrupt resource (<b>CmResourceTypeInterrupt</b>).</div>
<div> </div>
If <b>Class</b> = CM_RESOURCE_CONNECTION_CLASS_SERIAL, <b>Type</b> is set to one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="CM_RESOURCE_CONNECTION_TYPE_SERIAL_I2C"></a><a id="cm_resource_connection_type_serial_i2c"></a><dl>
<dt><b>CM_RESOURCE_CONNECTION_TYPE_SERIAL_I2C</b></dt>
</dl>
</td>
<td width="60%">
The device is connected to an I²C bus.

</td>
</tr>
<tr>
<td width="40%"><a id="CM_RESOURCE_CONNECTION_TYPE_SERIAL_SPI"></a><a id="cm_resource_connection_type_serial_spi"></a><dl>
<dt><b>CM_RESOURCE_CONNECTION_TYPE_SERIAL_SPI</b></dt>
</dl>
</td>
<td width="60%">
The device is connected to an SPI bus.

</td>
</tr>
<tr>
<td width="40%"><a id="CM_RESOURCE_CONNECTION_TYPE_SERIAL_UART"></a><a id="cm_resource_connection_type_serial_uart"></a><dl>
<dt><b>CM_RESOURCE_CONNECTION_TYPE_SERIAL_UART</b></dt>
</dl>
</td>
<td width="60%">
The device is connected to a serial port.

</td>
</tr>
</table>
 


### -field u.Connection.Reserved1

Not used.


### -field u.Connection.Reserved2

Not used.


### -field u.Connection.IdLowPart

Contains the lower 32 bits of the 64-bit connection ID.


### -field u.Connection.IdHighPart

Contains the upper 32 bits of the 64-bit connection ID.


## -remarks



A <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b> structure can describe either a raw (bus-relative) resource or a translated (system physical) resource, depending on the routine or IRP with which it is being used. For more information, see <a href="https://msdn.microsoft.com/dfc1376d-7a1a-421c-82ae-e183cac77ec8">Raw and Translated Resources</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541947">CM_FLOPPY_DEVICE_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541954">CM_FULL_RESOURCE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541967">CM_KEYBOARD_DEVICE_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541981">CM_PARTIAL_RESOURCE_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541994">CM_RESOURCE_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541998">CM_SCSI_DEVICE_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542003">CM_SERIAL_DEVICE_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a>



<a href="https://msdn.microsoft.com/03e3a656-c691-4aff-bcc8-4e0bc8390fd7">IO_RESOURCE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548371">IoConnectInterrupt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549203">IoGetDeviceProperty</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549608">IoReportResourceForDetection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561768">RtlCmDecodeMemIoResource</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561774">RtlCmEncodeMemIoResource</a>
 

 

