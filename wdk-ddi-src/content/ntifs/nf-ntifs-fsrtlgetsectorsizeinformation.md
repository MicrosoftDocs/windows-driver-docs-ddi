---
UID: NF:ntifs.FsRtlGetSectorSizeInformation
title: FsRtlGetSectorSizeInformation function (ntifs.h)
description: The FsRtlGetSectorSizeInformation routine retrieves the physical and logical sector size information for a storage volume.
old-location: ifsk\fsrtlgetsectorsizeinformation.htm
tech.root: ifsk
ms.assetid: 337E5450-8C90-48B7-B344-FB9420498D4F
ms.date: 04/16/2018
keywords: ["FsRtlGetSectorSizeInformation function"]
ms.keywords: FsRtlGetSectorSizeInformation, FsRtlGetSectorSizeInformation routine [Installable File System Drivers], ifsk.fsrtlgetsectorsizeinformation, ntifs/FsRtlGetSectorSizeInformation
f1_keywords:
 - "ntifs/FsRtlGetSectorSizeInformation"
 - "FsRtlGetSectorSizeInformation"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in starting with Windows 8.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlGetSectorSizeInformation
targetos: Windows
req.typenames: 
---

# FsRtlGetSectorSizeInformation function


## -description


The <b>FsRtlGetSectorSizeInformation</b> routine retrieves the physical and logical sector size information for a storage volume.


## -parameters




### -param DeviceObject

<p>The target device object for a storage device.</p>


### -param SectorSizeInfo [out]

A pointer to a caller supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_fs_sector_size_information">FILE_FS_SECTOR_SIZE_INFORMATION</a> structure.


## -returns



<b>FsRtlGetSectorSizeInformation</b> returns <b>STATUS_SUCCESS</b> if the sector size information is returned in <i>SectorSizeInfo</i>. Otherwise, another appropriate <b>NTSTATUS</b> value is returned such as the following.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BAD_DEVICE_TYPE</b></dt>
</dl>
</td>
<td width="60%">
The storage device reported an invalid sector size.

</td>
</tr>
</table>
 




## -remarks



This routine is used by file system drivers to retrieve sector size information from the storage device containing the volume. A file system driver typically maintains the device object sent in <i>RealDevice</i> in its  volume parameter block (VPD) for the storage volume.

Drivers other than file system drivers, can query sector size information using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryvolumeinformation">FltQueryVolumeInformation</a> or  <a href="https://msdn.microsoft.com/library/windows/hardware/ff567070">ZwQueryVolumeInformationFile</a> routines, or by sending an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-query-volume-information">IRP_MJ_QUERY_VOLUME_INFORMATION</a> request and specifying <b>FileFsSectorSizeInformation</b> as the file system information class.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_fs_sector_size_information">FILE_FS_SECTOR_SIZE_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryvolumeinformation">FltQueryVolumeInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-query-volume-information">IRP_MJ_QUERY_VOLUME_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567070">ZwQueryVolumeInformationFile</a>
 

 

