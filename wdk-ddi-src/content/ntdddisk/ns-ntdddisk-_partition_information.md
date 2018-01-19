---
UID: NS:ntdddisk._PARTITION_INFORMATION
title: _PARTITION_INFORMATION
author: windows-driver-content
description: The PARTITION_INFORMATION structure contains partition information for a partition with a traditional AT-style Master Boot Record (MBR).
old-location: storage\partition_information.htm
old-project: storage
ms.assetid: 06c3ed56-3640-431d-a4f0-bf3228a02cc2
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _PARTITION_INFORMATION, *PPARTITION_INFORMATION, PARTITION_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PARTITION_INFORMATION
req.alt-loc: ntdddisk.h
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
req.typenames: *PPARTITION_INFORMATION, PARTITION_INFORMATION
---

# _PARTITION_INFORMATION structure



## -description
The PARTITION_INFORMATION structure contains partition information for a partition with a traditional AT-style Master Boot Record (MBR). 



## -syntax

````
typedef struct _PARTITION_INFORMATION {
  LARGE_INTEGER StartingOffset;
  LARGE_INTEGER PartitionLength;
  ULONG         HiddenSectors;
  ULONG         PartitionNumber;
  UCHAR         PartitionType;
  BOOLEAN       BootIndicator;
  BOOLEAN       RecognizedPartition;
  BOOLEAN       RewritePartition;
} PARTITION_INFORMATION, *PPARTITION_INFORMATION;
````


## -struct-fields

### -field StartingOffset

Specifies the offset in bytes on drive where the partition begins.


### -field PartitionLength

Specifies the length in bytes of the partition. 


### -field HiddenSectors

Specifies the number of hidden sectors. 


### -field PartitionNumber

Specifies the number of the partition.


### -field PartitionType


### -field Indicates the system-defined MBR partition type. Possible values are as follows:
### -field 

<tr>
<th>Partition Type</th>
<th>Meaning</th>
</tr>
<tr>
<td>
PARTITION_ENTRY_UNUSED

</td>
<td>
Unused entry.

</td>
</tr>
<tr>
<td>
PARTITION_FAT_12 

</td>
<td>
Specifies a partition with 12-bit FAT entries.

</td>
</tr>
<tr>
<td>
PARTITION_XENIX_1 

</td>
<td>
Specifies a XENIX Type 1 partition.

</td>
</tr>
<tr>
<td>
PARTITION_XENIX_2

</td>
<td>
Specifies a XENIX Type 2 partition.

</td>
</tr>
<tr>
<td>
PARTITION_FAT_16

</td>
<td>
Specifies a partition with 16-bit FAT entries.

</td>
</tr>
<tr>
<td>
PARTITION_EXTENDED

</td>
<td>
Specifies an MS-DOS V4 extended partition.

</td>
</tr>
<tr>
<td>
PARTITION_HUGE

</td>
<td>
Specifies an MS-DOS V4 huge partition.

</td>
</tr>
<tr>
<td>
PARTITION_IFS

</td>
<td>
Specifies an IFS partition.

</td>
</tr>
<tr>
<td>
PARTITION_FAT32

</td>
<td>
Specifies a FAT32 partition.

</td>
</tr>
<tr>
<td>
PARTITION_FAT32_XINT13

</td>
<td>
<b>Windows 95/98: </b>Specifies a partition that uses extended INT 13 services.

</td>
</tr>
<tr>
<td>
PARTITION_XINT13_EXTENDED

</td>
<td>
<b>Windows 95/98: </b>Same as PARTITION_EXTENDED, but uses extended INT 13 services.

</td>
</tr>
<tr>
<td>
PARTITION_PREP

</td>
<td>
Specifies a PowerPC Reference Platform partition.

</td>
</tr>
<tr>
<td>
PARTITION_LDM

</td>
<td>
Specifies a logical disk manager partition.

</td>
</tr>
<tr>
<td>
PARTITION_UNIX

</td>
<td>
Specifies a UNIX partition.

</td>
</tr>
<tr>
<td>
PARTITION_NTFT

</td>
<td>
Specifies an NTFT partition. This value is used in combination (that is, bitwise logically ORed) with the other values in this table.

</td>
</tr>
</table>
 





</dl>

### -field BootIndicator

Indicates, when <b>TRUE</b>, that this partition is a bootable (active) partition for this device. When <b>FALSE</b>, this partition is not bootable. This member is set according to the partition list entry boot indicator returned by <a href="..\ntddk\nf-ntddk-ioreadpartitiontable.md">IoReadPartitionTable</a>. 


### -field RecognizedPartition

Indicates, when <b>TRUE</b>, that the system recognized the type of the partition. When <b>FALSE</b>, the system did not recognize the type of the partition. 


### -field RewritePartition

Indicates, when <b>TRUE</b>, that the partition information has changed. When <b>FALSE</b>, the partition information has not changed. This member has a value of <b>TRUE</b> when the partition has changed as a result of an <a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_set_drive_layout.md">IOCTL_DISK_SET_DRIVE_LAYOUT</a> IOCTL. This informs the system that the partition information needs to be rewritten.


## -remarks
The partition entry data in PARTITION_INFORMATION forms part of the drive layout information reported by the legacy routine <a href="..\ntddk\nf-ntddk-ioreadpartitiontable.md">IoReadPartitionTable</a> in the <a href="..\ntdddisk\ns-ntdddisk-_drive_layout_information.md">DRIVE_LAYOUT_INFORMATION</a> structure. DRIVE_LAYOUT_INFORMATION contains an array of PARTITION_INFORMATION structures pointed to by its <b>PartitionEntry</b> member. Each partition entry contains information for a partition on the drive. PARTITION_INFORMATION is also used with the legacy routine <a href="..\ntddk\nf-ntddk-iosetpartitioninformation.md">IoSetPartitionInformation</a> to change the properties of the partition, such as its type, recorded on the disk. 

In Windows 2000 and later operating systems, disk drivers should use structures <a href="..\ntdddisk\ns-ntdddisk-_drive_layout_information_ex.md">DRIVE_LAYOUT_INFORMATION_EX</a> and <a href="..\ntdddisk\ns-ntdddisk-_partition_information_ex.md">PARTITION_INFORMATION_EX</a> along with routines <a href="..\ntddk\nf-ntddk-ioreadpartitiontableex.md">IoReadPartitionTableEx</a> and <a href="..\ntddk\nf-ntddk-iosetpartitioninformationex.md">IoSetPartitionInformationEx</a> to read and alter partition information on the disk. 


## -see-also
<dl>
<dt>
<a href="..\ntddk\nf-ntddk-ioreadpartitiontable.md">IoReadPartitionTable</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-iosetpartitioninformation.md">IoSetPartitionInformation</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-ioreadpartitiontableex.md">IoReadPartitionTableEx</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-iosetpartitioninformationex.md">IoSetPartitionInformationEx</a>
</dt>
<dt>
<a href="..\ntdddisk\ns-ntdddisk-_drive_layout_information.md">DRIVE_LAYOUT_INFORMATION</a>
</dt>
<dt>
<a href="..\ntdddisk\ns-ntdddisk-_drive_layout_information_ex.md">DRIVE_LAYOUT_INFORMATION_EX</a>
</dt>
<dt>
<a href="..\ntdddisk\ns-ntdddisk-_partition_information_ex.md">PARTITION_INFORMATION_EX</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20PARTITION_INFORMATION structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

