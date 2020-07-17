---
UID: NS:ntddk._FILE_FS_SECTOR_SIZE_INFORMATION
title: _FILE_FS_SECTOR_SIZE_INFORMATION (ntddk.h)
description: The FILE_FS_SECTOR_SIZE_INFORMATION structure is used to query physical and logical sector size information for a file system volume.
old-location: ifsk\file_fs_sector_size_information.htm
tech.root: ifsk
ms.assetid: 24DEEDC7-B339-44DD-BF48-3BD59520EB8D
ms.date: 04/16/2018
keywords: ["_FILE_FS_SECTOR_SIZE_INFORMATION structure"]
ms.keywords: "*PFILE_FS_SECTOR_SIZE_INFORMATION, FILE_FS_SECTOR_SIZE_INFORMATION, FILE_FS_SECTOR_SIZE_INFORMATION structure [Installable File System Drivers], PFILE_FS_SECTOR_SIZE_INFORMATION, PFILE_FS_SECTOR_SIZE_INFORMATION structure pointer [Installable File System Drivers], SSINFO_FLAGS_ALIGNED_DEVICE, SSINFO_FLAGS_NO_SEEK_PENALTY, SSINFO_FLAGS_PARTITION_ALIGNED_ON_DEVICE, _FILE_FS_SECTOR_SIZE_INFORMATION, ifsk.file_fs_sector_size_information, ntddk/FILE_FS_SECTOR_SIZE_INFORMATION, ntddk/PFILE_FS_SECTOR_SIZE_INFORMATION"
f1_keywords:
 - "ntddk/FILE_FS_SECTOR_SIZE_INFORMATION"
 - "FILE_FS_SECTOR_SIZE_INFORMATION"
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available starting with Windows 7.
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
- ntddk.h
api_name:
- FILE_FS_SECTOR_SIZE_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: FILE_FS_SECTOR_SIZE_INFORMATION, *PFILE_FS_SECTOR_SIZE_INFORMATION
---

# _FILE_FS_SECTOR_SIZE_INFORMATION structure


## -description


The <b>FILE_FS_SECTOR_SIZE_INFORMATION</b> structure is used to query physical and logical sector size information for a file system volume. 


## -struct-fields




### -field LogicalBytesPerSector

Logical bytes per sector  reported by physical storage. This is the same value as the block size for used for Logical Block Addressing (LBA).


### -field PhysicalBytesPerSectorForAtomicity

Actual bytes per sector reported by physical storage used for an atomic write.


### -field PhysicalBytesPerSectorForPerformance

Bytes per sector reported by physical storage for best performance.


### -field FileSystemEffectivePhysicalBytesPerSectorForAtomicity

The portion of <b>PhysicalBytesPerSectorForAtomicity</b> considered as the physical sector size by the file system.


### -field Flags

Flags for sector alignment and performance capabilities. This value is a bitwise OR combination of the following:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="SSINFO_FLAGS_ALIGNED_DEVICE"></a><a id="ssinfo_flags_aligned_device"></a><dl>
<dt><b>SSINFO_FLAGS_ALIGNED_DEVICE</b></dt>
</dl>
</td>
<td width="60%">
Logical sectors of the storage device are aligned to physical sector boundaries.

</td>
</tr>
<tr>
<td width="40%"><a id="SSINFO_FLAGS_PARTITION_ALIGNED_ON_DEVICE"></a><a id="ssinfo_flags_partition_aligned_on_device"></a><dl>
<dt><b>SSINFO_FLAGS_PARTITION_ALIGNED_ON_DEVICE</b></dt>
</dl>
</td>
<td width="60%">
The partition is aligned to physical sector boundaries on the storage device.

</td>
</tr>
<tr>
<td width="40%"><a id="SSINFO_FLAGS_NO_SEEK_PENALTY"></a><a id="ssinfo_flags_no_seek_penalty"></a><dl>
<dt><b>SSINFO_FLAGS_NO_SEEK_PENALTY</b></dt>
</dl>
</td>
<td width="60%">
The storage device has no seek penalty.

</td>
</tr>
<tr>
<td width="40%"><a id="SSINFO_FLAGS_PARTITION_ALIGNED_ON_DEVICE"></a><a id="ssinfo_flags_partition_aligned_on_device"></a><dl>
<dt><b>SSINFO_FLAGS_PARTITION_ALIGNED_ON_DEVICE</b></dt>
</dl>
</td>
<td width="60%">
The storage device supports the TRIM operation.

</td>
</tr>
</table>
 


### -field ByteOffsetForSectorAlignment

The offset, in bytes, of the beginning of the first logical sector within the first physical sector. This member is set to <b>SSINFO_OFFSET_UNKNOWN</b> if proper device information is not available to calculate the value.


### -field ByteOffsetForPartitionAlignment

The offset value, in bytes, used to align the partition to a physical sector boundary. This member is set to <b>SSINFO_OFFSET_UNKNOWN</b> if proper device information is not available to calculate the value.


## -remarks



This information can be queried in either of the following ways: 

<ul>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryvolumeinformation">FltQueryVolumeInformation</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567070">ZwQueryVolumeInformationFile</a>, passing <b>FileFsSectorSizeInformation</b> as the value of <i>FileInformationClass</i> and passing a caller-allocated, <b>FILE_FS_SECTOR_SIZE_INFORMATION</b>-structured buffer as the value of <i>FileInformation</i>. 

</li>
<li>
Create an IRP with major function code <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-query-volume-information">IRP_MJ_QUERY_VOLUME_INFORMATION</a>. 

</li>
<li>
Call <a href="https://msdn.microsoft.com/library/windows/hardware/hh920377">FsRtlGetSectorSizeInformation</a> with a pointer to a <b>FILE_FS_SECTOR_SIZE_INFORMATION</b>-structured buffer. The  <b>FileSystemEffectivePhysicalBytesPerSectorForAtomicity</b> member will not have a value initialized by  the file system when this structure is returned from <b>FsRtlGetSectorSizeInformation</b>. A file system driver will typically call this function and then set its own value for  <b>FileSystemEffectivePhysicalBytesPerSectorForAtomicity</b>.

</li>
</ul>
No specific access rights are required to query this information. Thus this information is available as long as the volume is accessed through an open handle to the volume itself, or to a file or directory on the volume. 

The size of the buffer passed in the <i>FileInformation</i> parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryvolumeinformation">FltQueryVolumeInformation</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567070">ZwQueryVolumeInformationFile</a> must be at least <b>sizeof</b> (FILE_FS_SECTOR_SIZE_INFORMATION). 

The file system uses the value of <b>LogicalBytesPerSector</b> to determine the size of an allocation unit. The <b>LogicalBytesPerSector</b> member of this structure is equivalent to the <b>BytesPerSector</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_fs_size_information">FILE_FS_SIZE_INFORMATION</a>  and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_fs_full_size_information">FILE_FS_FULL_SIZE_INFORMATION</a> structures.

If the system is unable to determine values for <b>PhysicalBytesPerSectorForAtomicity</b> and <b>PhysicalBytesPerSectorForPerformance</b> from the storage device, then they are set to the value of <b>LogicalBytesPerSector.</b>




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_fs_full_size_information">FILE_FS_FULL_SIZE_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_fs_size_information">FILE_FS_SIZE_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryvolumeinformation">FltQueryVolumeInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh920377">FsRtlGetSectorSizeInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-query-volume-information">IRP_MJ_QUERY_VOLUME_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567070">ZwQueryVolumeInformationFile</a>
 

 

