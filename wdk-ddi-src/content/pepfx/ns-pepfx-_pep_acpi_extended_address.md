---
UID: NS:pepfx._PEP_ACPI_EXTENDED_ADDRESS
title: _PEP_ACPI_EXTENDED_ADDRESS (pepfx.h)
description: The PEP_ACPI_EXTENDED_ADDRESS structure is used to report resource usage in the address space such as memory and IO.
old-location: kernel\pep_acpi_extended_address.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PEP_ACPI_EXTENDED_ADDRESS structure"]
ms.keywords: "*PPEP_ACPI_EXTENDED_ADDRESS, 0 - Consumer/Producer flag, 0 - Write status, 0 to 1 - Range, 0 to 7 - Reserved, 1 - Decode type, 1 to 2 - Memory attributes (MEM), 2 - Minimum address fixed, 2 to 3 - Reserved, 3 - Max address fixed, 3 to 4 - Memory attributes (MTP), 4 - IO to memory translation, 4 to 7 - Reserved, 5 - Memory to IO translation, 5 - Sparse translation, 6 to 7 - Reserved, PEP_ACPI_EXTENDED_ADDRESS, PEP_ACPI_EXTENDED_ADDRESS structure [Kernel-Mode Driver Architecture], PPEP_ACPI_EXTENDED_ADDRESS, PPEP_ACPI_EXTENDED_ADDRESS structure pointer [Kernel-Mode Driver Architecture], _PEP_ACPI_EXTENDED_ADDRESS, kernel.pep_acpi_extended_address, pepfx/PEP_ACPI_EXTENDED_ADDRESS, pepfx/PPEP_ACPI_EXTENDED_ADDRESS"
req.header: pepfx.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
req.typenames: PEP_ACPI_EXTENDED_ADDRESS, *PPEP_ACPI_EXTENDED_ADDRESS
f1_keywords:
 - _PEP_ACPI_EXTENDED_ADDRESS
 - pepfx/_PEP_ACPI_EXTENDED_ADDRESS
 - PPEP_ACPI_EXTENDED_ADDRESS
 - pepfx/PPEP_ACPI_EXTENDED_ADDRESS
 - PEP_ACPI_EXTENDED_ADDRESS
 - pepfx/PEP_ACPI_EXTENDED_ADDRESS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - PEP_ACPI_EXTENDED_ADDRESS
---

# _PEP_ACPI_EXTENDED_ADDRESS structure (pepfx.h)


## -description

The <b>PEP_ACPI_EXTENDED_ADDRESS</b> structure is used to report resource usage in the address space such as memory and IO.

## -struct-fields

### -field Type

A <a href="/windows-hardware/drivers/ddi/pepfx/ne-pepfx-_pep_acpi_resource_type">PEP_ACPI_RESOURCE_TYPE</a> enumeration value describing this resource.

### -field Flags

A <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_resource_flags">PEP_ACPI_RESOURCE_FLAGS</a> structure describing this resource.

### -field ResourceFlags

Indicates the type of resource this structure describes.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0</dt>
</dl>
</td>
<td width="60%">
Indicates that this resource is a memory range.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>1</dt>
</dl>
</td>
<td width="60%">
Indicates that this resource is an IO range.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>2</dt>
</dl>
</td>
<td width="60%">
Indicates that this resource is a bus number range.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>3-191</dt>
</dl>
</td>
<td width="60%">
These values are reserved for future use.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>192-255</dt>
</dl>
</td>
<td width="60%">
These values are reserved for use by the hardware vendor.

</td>
</tr>
</table>

### -field GeneralFlags

A value containing the bit flags that are common to all resource types. 

<table>
<tr>
<th>Bit(s)</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="0_-_Consumer_Producer_flag"></a><a id="0_-_consumer_producer_flag"></a><a id="0_-_CONSUMER_PRODUCER_FLAG"></a><dl>
<dt><b>0 - Consumer/Producer flag</b></dt>
</dl>
</td>
<td width="60%">
When set, this indicates that the device consumes this resource.

</td>
</tr>
<tr>
<td width="40%"><a id="1_-_Decode_type"></a><a id="1_-_decode_type"></a><a id="1_-_DECODE_TYPE"></a><dl>
<dt><b>1 - Decode type</b></dt>
</dl>
</td>
<td width="60%">
When set, indicates that this bridge subtractively decodes the address. This applies to top level bridges only. 

When not set, indicates that this bridge positively decodes this address.

</td>
</tr>
<tr>
<td width="40%"><a id="2_-_Minimum_address_fixed"></a><a id="2_-_minimum_address_fixed"></a><a id="2_-_MINIMUM_ADDRESS_FIXED"></a><dl>
<dt><b>2 - Minimum address fixed</b></dt>
</dl>
</td>
<td width="60%">
When set, indicates that the minimum address is fixed.

</td>
</tr>
<tr>
<td width="40%"><a id="3_-_Max_address_fixed"></a><a id="3_-_max_address_fixed"></a><a id="3_-_MAX_ADDRESS_FIXED"></a><dl>
<dt><b>3 - Max address fixed</b></dt>
</dl>
</td>
<td width="60%">
When set, indicates that the maximum address is fixed. 

</td>
</tr>
<tr>
<td width="40%"><a id="4_to_7_-_Reserved"></a><a id="4_to_7_-_reserved"></a><a id="4_TO_7_-_RESERVED"></a><dl>
<dt><b>4 to 7 - Reserved</b></dt>
</dl>
</td>
<td width="60%">
These bits are reserved and must be set to zero.

</td>
</tr>
</table>

### -field TypeSpecificFlags

The value of this member is dependent on the value in <b>ResourceFlags</b> member. The flags for each resource type are described in the tables below.


Memory Resource (<b>ResourceFlags</b> = <b>0</b>)



<table>
<tr>
<th>Bit(s)</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="0_-_Write_status"></a><a id="0_-_write_status"></a><a id="0_-_WRITE_STATUS"></a><dl>
<dt><b>0 - Write status</b></dt>
</dl>
</td>
<td width="60%">
When set, indicates that this memory range is available for reading and writing. Otherwise, this indicates that this memory range is read-only.

</td>
</tr>
<tr>
<td width="40%"><a id="1_to_2_-_Memory_attributes__MEM_"></a><a id="1_to_2_-_memory_attributes__mem_"></a><a id="1_TO_2_-_MEMORY_ATTRIBUTES__MEM_"></a><dl>
<dt><b>1 to 2 - Memory attributes (MEM)</b></dt>
</dl>
</td>
<td width="60%">
<b>0</b> - Indicates the memory is non-cacheable.

<b>1</b> - Indicates the memory is cacheable.

<b>2</b> - Indicates the memory is cacheable and supports write combining.

<b>3</b>  - The memory is cacheable and prefetchable.

</td>
</tr>
<tr>
<td width="40%"><a id="3_to_4_-_Memory_attributes__MTP_"></a><a id="3_to_4_-_memory_attributes__mtp_"></a><a id="3_TO_4_-_MEMORY_ATTRIBUTES__MTP_"></a><dl>
<dt><b>3 to 4 - Memory attributes (MTP)</b></dt>
</dl>
</td>
<td width="60%">
These bits are only defined if this memory resource describes system RAM.  

<b>0</b> - Address range memory: This range is available RAM usable by the operating system.

<b>1</b> - Address range reserved: This range of addresses is in use or reserved by the system
and is not to be included in the allocatable memory pool of the
operating system's memory manager.

<b>2</b> - Address range ACPI: ACPI Reclaim Memory. This range is available RAM usable by
the OS after it reads the ACPI tables. 

<b>3</b> - Address Range NVS: ACPI NVS Memory. This range of addresses is in use or
reserved by the system and must not be used by the operating
system. This range is required to be saved and restored across
an NVS sleep.

</td>
</tr>
<tr>
<td width="40%"><a id="5_-_Memory_to_IO_translation"></a><a id="5_-_memory_to_io_translation"></a><a id="5_-_MEMORY_TO_IO_TRANSLATION"></a><dl>
<dt><b>5 - Memory to IO translation</b></dt>
</dl>
</td>
<td width="60%">
<b>0</b> - Type-static: This resource is memory on the primary and secondary sides of the bridge.

<b>1</b> - Type-translation: This resource is memory on the secondary side of the bridge and IO on the primary side of the bridge.

</td>
</tr>
<tr>
<td width="40%"><a id="6_to_7_-_Reserved"></a><a id="6_to_7_-_reserved"></a><a id="6_TO_7_-_RESERVED"></a><dl>
<dt><b>6 to 7 - Reserved</b></dt>
</dl>
</td>
<td width="60%">
These bits are reserved and must be set to zero.

</td>
</tr>
</table>
 


IO Resource (<b>ResourceFlags</b> = <b>1</b>)



<table>
<tr>
<th>Bit(s)</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="0_to_1_-_Range"></a><a id="0_to_1_-_range"></a><a id="0_TO_1_-_RANGE"></a><dl>
<dt><b>0 to 1 - Range</b></dt>
</dl>
</td>
<td width="60%">
<b>0</b> - Reserved.

<b>1</b> - Non-ISA ranges only. This flag is for bridges on systems with multiple bridges. Setting this
bit means the memory window specified in this descriptor is limited to the non-ISA IO
addresses that fall within the specified window. The non-ISA IO ranges are: n100-n3FF,
n500-n7FF, n900-nBFF, nD00-nFFF. This bit can only be set for bridges entirely
configured through the ACPI namespace.


<b>2</b> - ISA ranges only. This flag is for bridges on systems with multiple bridges. Setting this bit
means the memory window specified in this descriptor is limited to the ISA IO addresses
that fall within the specified window. The ISA IO ranges are: n000-n0FF, n400-n4FF,
n800-n8FF, nC00-nCFF. This bit can only be set for bridges entirely configured through
the ACPI namespace.


<b>3</b> - The memory window covers the entire range


</td>
</tr>
<tr>
<td width="40%"><a id="2_to_3_-_Reserved"></a><a id="2_to_3_-_reserved"></a><a id="2_TO_3_-_RESERVED"></a><dl>
<dt><b>2 to 3 - Reserved</b></dt>
</dl>
</td>
<td width="60%">
These bits are reserved and must be set to zero.

</td>
</tr>
<tr>
<td width="40%"><a id="4_-_IO_to_memory_translation"></a><a id="4_-_io_to_memory_translation"></a><a id="4_-_IO_TO_MEMORY_TRANSLATION"></a><dl>
<dt><b>4 - IO to memory translation</b></dt>
</dl>
</td>
<td width="60%">
<b>0</b> - Type-static: This resource is IO on the primary and secondary sides of the bridge.

<b>1</b> - Type-translation: This resource is IO on the secondary side of the bridge and memory on the primary side of the bridge.

</td>
</tr>
<tr>
<td width="40%"><a id="5_-_Sparse_translation"></a><a id="5_-_sparse_translation"></a><a id="5_-_SPARSE_TRANSLATION"></a><dl>
<dt><b>5 - Sparse translation</b></dt>
</dl>
</td>
<td width="60%">
This bit is only meaningful if bit 4 (IO to memory translation) is set.


<b>0</b> - Dense translation: The primary-side memory address of any specific IO port within the
secondary-side range can be found using the following function. 

<i>     address = port + TranslationAddress</i>

<b>1</b> - Sparse translation: The primary-side memory address of any specific IO port within the
secondary-side range can be found using the following function.

<i>address = (((port & 0xFFFc) << 10) || (port & 0xFFF)) + TranslationAddress</i>

In the address used to access the IO port, bits 2 to 11 must be identical
to bits 12 to 21, this gives four bytes of IO ports on each 4 KB page.

</td>
</tr>
<tr>
<td width="40%"><a id="6_to_7_-_Reserved"></a><a id="6_to_7_-_reserved"></a><a id="6_TO_7_-_RESERVED"></a><dl>
<dt><b>6 to 7 - Reserved</b></dt>
</dl>
</td>
<td width="60%">
These bits are reserved and must be set to zero.

</td>
</tr>
</table>
 


Bus Number Range Resource (<b>ResourceFlags</b> = <b>2</b>)



<table>
<tr>
<th>Bit(s)</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="0_to_7_-_Reserved"></a><a id="0_to_7_-_reserved"></a><a id="0_TO_7_-_RESERVED"></a><dl>
<dt><b>0 to 7 - Reserved</b></dt>
</dl>
</td>
<td width="60%">
These bits are reserved and must be set to zero.

</td>
</tr>
</table>

### -field RevisionId

Indicates the revision of the extended address space descriptor detailed by this structure. For ACPI 3.0, this value is 1.

### -field Reserved

### -field Granularity

A bit mask indicating which bits have been decoded.

### -field MinimumAddress

The minimum starting address. For bridges that translate addresses, this is the address space on the secondary side of the bridge.

### -field MaximumAddress

The maximum starting address. For bridges that translate addresses, this is the address space
on the secondary side of the bridge.

### -field TranslationAddress

For bridges that translate addresses across the bridge, this is the
address on the primary side.

### -field AddressLength

The address length.

### -field TypeAttribute

Indicates attributes that are specific to the resource type that is specified in the <b>ResourceFlags</b> member. If <b>ResourceFlags</b> is zero, this value is zero, otherwise the meaning of the value can be found in the <i>UEFI Specification</i> in the section titled <b>GetMemoryMap()</b>.

### -field DescriptorName

The name of this resource descriptor.
