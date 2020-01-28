---
UID: NS:ks.__unnamed_struct_41
title: KS_FRAMING_ITEM (ks.h)
description: The KS_FRAMING_ITEM structure is used to declare allocator requirements on a kernel-mode pin.
old-location: stream\ks_framing_item.htm
tech.root: stream
ms.assetid: cd7d4ef7-f8ad-467f-aa5b-28b131941094
ms.date: 04/23/2018
ms.keywords: "*PKS_FRAMING_ITEM, KSALLOCATOR_FLAG_CAN_ALLOCATE, KSALLOCATOR_FLAG_DEVICE_SPECIFIC, KSALLOCATOR_FLAG_INSIST_ON_FRAMESIZE_RATIO, KSALLOCATOR_FLAG_PARTIAL_READ_SUPPORT, KSALLOCATOR_REQUIREMENTF_PREFERENCES_ONLY, KS_FRAMING_ITEM, KS_FRAMING_ITEM structure [Streaming Media Devices], PKS_FRAMING_ITEM, PKS_FRAMING_ITEM structure pointer [Streaming Media Devices], ks-struct_8ddb4478-636f-4cd4-b4c1-663a20070cef.xml, ks/KS_FRAMING_ITEM, ks/PKS_FRAMING_ITEM, stream.ks_framing_item"
f1_keywords:
 - "ks/KS_FRAMING_ITEM"
req.header: ks.h
req.include-header: Ks.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- KS_FRAMING_ITEM
product:
- Windows
targetos: Windows
req.typenames: KS_FRAMING_ITEM, *PKS_FRAMING_ITEM
---

# KS_FRAMING_ITEM structure


## -description


The KS_FRAMING_ITEM structure is used to declare allocator requirements on a kernel-mode pin.


## -struct-fields




### -field MemoryType

Specifies the type of memory used for buffers and data frames. There is a partial correspondence between this member and the <b>PoolType</b> member in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksallocator_framing">KSALLOCATOR_FRAMING</a> structure. The two members differ in that <b>PoolType</b> allows only paged or nonpaged pool. <b>MemoryType</b> can have any of the values listed in the following table.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
KSMEMORY_TYPE_WILDCARD / KSMEMORY_TYPE_DONT_CARE / KSTYPE_DONT_CARE

</td>
<td>
Indicates memory allocation can be any type of memory.

</td>
</tr>
<tr>
<td>
KSMEMORY_TYPE_SYSTEM

</td>
<td>
Indicates memory allocation must be system memory.

</td>
</tr>
<tr>
<td>
KSMEMORY_TYPE_USER

</td>
<td>
Indicates memory allocation must be user-mode memory.

</td>
</tr>
<tr>
<td>
KSMEMORY_TYPE_KERNEL_PAGED

</td>
<td>
Indicates memory allocation must be kernel paged memory. This corresponds to the <b>PoolType</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksallocator_framing">KSALLOCATOR_FRAMING</a> structure set to <b>PagedPool</b> and the <b>RequirementsFlags</b> member of this structure set to SYSTEM_MEMORY.

</td>
</tr>
<tr>
<td>
KSMEMORY_TYPE_KERNEL_NONPAGED

</td>
<td>
Indicates memory allocation must be kernel nonpaged memory. This corresponds to the <b>PoolType</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksallocator_framing">KSALLOCATOR_FRAMING</a> structure set to <b>NonPagedPool</b> and the <b>RequirementsFlags</b> member of this structure set to SYSTEM_MEMORY.

</td>
</tr>
<tr>
<td>
KSMEMORY_TYPE_DEVICE_UNKNOWN

</td>
<td>
Indicates device memory allocation type is not specified.

</td>
</tr>
</table>
 


### -field BusType

Specifies the physical bus accessing the physical memory specified by <i>MemoryType</i>. Use this field to determine a compatible memory type based on the bus that is used for the connection medium. This distinction is crucial when a pin exposes different memory types based on the connection medium. <b>BusType</b> can have any of the values listed in the following table.

<table>
<tr>
<th>Type</th>
<th>Description</th>
</tr>
<tr>
<td>
GUID_BUS_TYPE_PCI

</td>
<td>
Peripheral component interconnect bus.

</td>
</tr>
<tr>
<td>
GUID_BUS_TYPE_USB

</td>
<td>
Universal serial bus.

</td>
</tr>
<tr>
<td>
GUID_BUS_TYPE_1394

</td>
<td>
IEEE 1394 serial bus.

</td>
</tr>
<tr>
<td>
GUID_BUS_TYPE_AVC

</td>
<td>
Audio/video control bus.

</td>
</tr>
<tr>
<td>
GUID_61883_CLASS

</td>
<td>
61883 protocol bus.

</td>
</tr>
</table>
 


### -field MemoryFlags

Specifies that the connection point is responsible for frame allocation. Should be set to KSALLOCATOR_REQUIREMENTF_MUST_ALLOCATE.


### -field BusFlags

Not used.  


### -field Flags

Similar to the <b>OptionsFlags</b> and <b>RequirementsFlags</b> union in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksallocator_framing">KSALLOCATOR_FRAMING</a> structure, with the addition of the following flags that add support for pipes.



##### )



##### )



###### )



##### )



##### )


### -field Frames

Specifies the total number of allowable outstanding frames. Corresponds to the <b>Frames</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksallocator_framing">KSALLOCATOR_FRAMING</a> structure.


### -field FileAlignment

Requirement for frame alignment. Corresponds to the <b>FileAlignment</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksallocator_framing">KSALLOCATOR_FRAMING</a> structure.


### -field FramePitch

 


### -field MemoryTypeWeight

A value of type ULONG that specifies the pin-wide weight of this memory type.


### -field PhysicalRange

A structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ks_framing_range">KS_FRAMING_RANGE</a> that specifies the physical limit of frame sizes.


### -field FramingRange

A structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ks_framing_range_weighted">KS_FRAMING_RANGE_WEIGHTED</a> that specifies the optimal range of frame sizes.


## -remarks



Do not set KSALLOCATOR_FLAG_CAN_ALLOCATE to indicate memory addressing capability. A filter might be able to access the device-specific memory over a device-specific bus by referencing the memory address on this bus, and yet not support the protocol to allocate this device-specific memory.

Each <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksallocator_framing_ex">KSALLOCATOR_FRAMING_EX</a> instance contains one or more framing items.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksallocator_framing">KSALLOCATOR_FRAMING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksallocator_framing_ex">KSALLOCATOR_FRAMING_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ks_compression">KS_COMPRESSION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ks_framing_range">KS_FRAMING_RANGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ks_framing_range_weighted">KS_FRAMING_RANGE_WEIGHTED</a>
 

 

