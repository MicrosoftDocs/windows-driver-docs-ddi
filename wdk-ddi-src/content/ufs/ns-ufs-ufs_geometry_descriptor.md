---
UID: NS:ufs.__unnamed_struct_3
title: UFS_GEOMETRY_DESCRIPTOR (ufs.h)
description: UFS_GEOMETRY_DESCRIPTOR describes a device's geometric parameters.
old-location: storage\ufs_geometry_descriptor.htm
tech.root: storage
ms.assetid: DD3AEB66-E36B-4F18-AFEC-D344132D4B8C
ms.date: 03/29/2018
keywords: ["UFS_GEOMETRY_DESCRIPTOR structure"]
ms.keywords: "*PUFS_GEOMETRY_DESCRIPTOR, PUFS_GEOMETRY_DESCRIPTOR, PUFS_GEOMETRY_DESCRIPTOR structure pointer [Storage Devices], UFS_GEOMETRY_DESCRIPTOR, UFS_GEOMETRY_DESCRIPTOR structure [Storage Devices], storage.ufs_geometry_descriptor, ufs/PUFS_GEOMETRY_DESCRIPTOR, ufs/UFS_GEOMETRY_DESCRIPTOR"
f1_keywords:
 - "ufs/UFS_GEOMETRY_DESCRIPTOR"
 - "UFS_GEOMETRY_DESCRIPTOR"
req.header: ufs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
- Ufs.h
api_name:
- UFS_GEOMETRY_DESCRIPTOR
targetos: Windows
req.typenames: UFS_GEOMETRY_DESCRIPTOR, *PUFS_GEOMETRY_DESCRIPTOR
---

# UFS_GEOMETRY_DESCRIPTOR structure


## -description


<b>UFS_GEOMETRY_DESCRIPTOR</b> describes a device's geometric parameters.


## -struct-fields




### -field bLength

Specifies the length of the descriptor.


### -field bDescriptorIDN

Specifies the type of the descriptor. This descriptor will have a value of<b> UFS_DESC_GEOMETRY_IDN</b>.




### -field bMediaTechnology

Reserved for future use.


### -field Reserved1

Reserved for future use.


### -field qTotalRawDeviceCapacity

Specifies the total raw device capacity. Expressed in units of 512 bytes.


### -field bMaxNumberLU

Specifies the maximum number of logical unit(s) supported by the UFS (Universal Flash Storage). Contains one of the following values:

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>8 logical units.</td>
</tr>
<tr>
<td>0x01</td>
<td>32 logical units.</td>
</tr>
<tr>
<td>Other Values</td>
<td>Reserved for future use.</td>
</tr>
</table>
 


### -field dSegmentSize

Specifies the segment size of the device in units of 512 bytes.


### -field bAllocationUnitSize

Specifies the allocation unit size in number of segments.


### -field bMinAddrBlockSize

Specifies the minimum addressable block size in units of 512 bytes. The minium size is 4 KB or a value of 0x08.


### -field bOptimalReadBlockSize

Specifies the optimal read block size in units of 512 bytes.


### -field bOptimalWriteBlockSize

Specifies the optimal write block size in units of 512 bytes. <b>bOptimalWriteBlockSize</b> is equal to or greater than <b>bMinAddrBlockSize</b>.


### -field bMaxInBufferSize

Specifies the max size of the data-in buffer in units of 512 bytes. The minium size is 4 KB or a value of 0x08.


### -field bMaxOutBufferSize

Specifies the max size of the data-out buffer in units of 512 bytes. The minium size is 4 KB or a value of 0x08.


### -field bRPMB_ReadWriteSize

Specifies the maximum number of Replay Protected Memory Block (RPMB) frames allowed in Security Protocol In and Security
Protocol Out. Each frame is 256-bytes. 


### -field bDynamicCapacityResourcePolicy

Specifies a device's spare blocks
resource management policy. Contains one of the following values:

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>Spare blocks resource management policy is
per logical unit.</td>
</tr>
<tr>
<td>0x01</td>
<td>Spare blocks resource management policy is
per memory type.</td>
</tr>
</table>
 


### -field bDataOrdering

Specifies if a device supports out-of-order data transfer. Contains one of the following values:

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>Out-of-order data transfer is not supported.</td>
</tr>
<tr>
<td>0x01</td>
<td>Out-of-order data transfer is supported.</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved for future use.</td>
</tr>
</table>
 


### -field bMaxContexIDNumber

Specifies the max number of contexts supported by a device. This number must be greater than 5.


### -field bSysDataTagUnitSize

Specifies the system data tag
unit size.


### -field bSysDataTagResSize

Specifies the maximum size in bytes allocated by
the device to handle system data.


### -field bSupportedSecRTypes

Specifies the supported Secure Removal types. The first 3 bits of the variable are flags that represent different supported Secure Removal types. 

<table>
<tr>
<th>Bit</th>
<th>Description</th>
</tr>
<tr>
<td>0</td>
<td>Information removed with an erase of the physical memory. </td>
</tr>
<tr>
<td>1</td>
<td>Information removed by overwriting the
addressed locations with a single character
followed by an erase.</td>
</tr>
<tr>
<td>2</td>
<td>Information removed by overwriting the
addressed locations with a character, its
complement, then a random character.</td>
</tr>
<tr>
<td>3</td>
<td>Information removed using a vendor-defined
mechanism.</td>
</tr>
<tr>
<td>4-7</td>
<td>Reserved for future use.</td>
</tr>
</table>
 


### -field wSupportedMemoryTypes

Specifies the supported memory types in a bitmap.

<table>
<tr>
<th>Bit</th>
<th>Description</th>
</tr>
<tr>
<td>0</td>
<td>A normal memory type is supported.</td>
</tr>
<tr>
<td>1</td>
<td>A system code memory type is supported.</td>
</tr>
<tr>
<td>2</td>
<td>A non-persistent memory type is supported.</td>
</tr>
<tr>
<td>3</td>
<td>Enhanced memory type 1 is supported.</td>
</tr>
<tr>
<td>4</td>
<td>Enhanced memory type 2 is supported.</td>
</tr>
<tr>
<td>5</td>
<td>Enhanced memory type 3 is supported.</td>
</tr>
<tr>
<td>6</td>
<td>Enhanced memory type 4 is supported.</td>
</tr>
<tr>
<td>7-14</td>
<td>Reserved for future use.</td>
</tr>
<tr>
<td>15</td>
<td>A RPMB memory type is supported.</td>
</tr>
</table>
 


### -field dSystemCodeMaxNAllocU

Specifies the maximum number of allocation units for the System Code for a device.


### -field wSystemCodeCapAdjFac

Species the Capacity Adjustment Factor for the System Code
memory type.


### -field dNonPersistMaxNAllocU

Species the maximum number of Allocation Units for a non-persistent memory type.


### -field wNonPersistCapAdjFac

Specifies the capacity adjustment factor for the non-persistent memory type.


### -field dEnhanced1MaxNAllocU

specifies the max number of Allocation Units for the enhanced
memory type 1.


### -field wEnhanced1CapAdjFac

specifies the Capacity Adjustment Factor for the enhanced
memory type 1.


### -field dEnhanced2MaxNAllocU

specifies the max number of Allocation Units for the enhanced
memory type 2.


### -field wEnhanced2CapAdjFac

specifies the Capacity Adjustment Factor for the enhanced
memory type 2.


### -field dEnhanced3MaxNAllocU

specifies the max number of Allocation Units for the enhanced
memory type 3.


### -field wEnhanced3CapAdjFac

specifies the Capacity Adjustment Factor for the enhanced
memory type 3.


### -field dEnhanced4MaxNAllocU

specifies the max number of Allocation Units for the enhanced
memory type 4.


### -field wEnhanced4CapAdjFac

specifies the Capacity Adjustment Factor for the enhanced
memory type 4.


### -field dOptimalLogicalBlockSize

Specifies the optimal logical block size.


## -remarks



If the size of the data transferred exceeds the number of frames <b>bRPMB_ReadWriteSize</b>, it will be done in multiple Security commands.

The Capacity Adjustment Factor value for a normal memory type is equal to 1.



