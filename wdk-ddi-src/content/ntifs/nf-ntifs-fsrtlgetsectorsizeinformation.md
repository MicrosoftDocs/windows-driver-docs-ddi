---
UID: NF:ntifs.FsRtlGetSectorSizeInformation
title: FsRtlGetSectorSizeInformation function
author: windows-driver-content
description: The FsRtlGetSectorSizeInformation routine retrieves the physical and logical sector size information for a storage volume.
old-location: ifsk\fsrtlgetsectorsizeinformation.htm
old-project: ifsk
ms.assetid: 337E5450-8C90-48B7-B344-FB9420498D4F
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: ntifs/FsRtlGetSectorSizeInformation, FsRtlGetSectorSizeInformation routine [Installable File System Drivers], FsRtlGetSectorSizeInformation, ifsk.fsrtlgetsectorsizeinformation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FsRtlGetSectorSizeInformation
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlGetSectorSizeInformation function


## -description


The <b>FsRtlGetSectorSizeInformation</b> routine retrieves the physical and logical sector size information for a storage volume.


## -syntax


````
NTSTATUS FsRtlGetSectorSizeInformation(
  _In_  PDEVICE_OBJECT                   RealDevice,
  _Out_ PFILE_FS_SECTOR_SIZE_INFORMATION SectorSizeInfo
);
````


## -parameters




### -param DeviceObject

TBD


### -param SectorSizeInfo [out]

A pointer to a caller supplied <a href="..\ntddk\ns-ntddk-_file_fs_sector_size_information.md">FILE_FS_SECTOR_SIZE_INFORMATION</a> structure.


#### - RealDevice [in]

The target device object for a storage device.


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

Drivers other than file system drivers, can query sector size information using the <a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformation.md">FltQueryVolumeInformation</a> or  <a href="..\ntifs\nf-ntifs-zwqueryvolumeinformationfile.md">ZwQueryVolumeInformationFile</a> routines, or by sending an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549318">IRP_MJ_QUERY_VOLUME_INFORMATION</a> request and specifying <b>FileFsSectorSizeInformation</b> as the file system information class.




## -see-also

<a href="..\ntddk\ns-ntddk-_file_fs_sector_size_information.md">FILE_FS_SECTOR_SIZE_INFORMATION</a>



<a href="..\ntifs\nf-ntifs-zwqueryvolumeinformationfile.md">ZwQueryVolumeInformationFile</a>



<a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformation.md">FltQueryVolumeInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549318">IRP_MJ_QUERY_VOLUME_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlGetSectorSizeInformation routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

