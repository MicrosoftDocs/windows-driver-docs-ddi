---
UID: NS:ntddk._FILE_FS_FULL_SIZE_INFORMATION_EX
title: _FILE_FS_FULL_SIZE_INFORMATION_EX (ntddk.h)
description: Used in a request to query sector size information for a file system volume.
tech.root: ifsk
ms.assetid: a7d7b036-3f47-4e6d-87df-1578300e095c
ms.date: 09/30/2018
keywords: ["_FILE_FS_FULL_SIZE_INFORMATION_EX structure"]
f1_keywords:
 - "ntddk/_FILE_FS_FULL_SIZE_INFORMATION_EX"
ms.keywords: _FILE_FS_FULL_SIZE_INFORMATION_EX, FILE_FS_FULL_SIZE_INFORMATION_EX, *PFILE_FS_FULL_SIZE_INFORMATION_EX, 
req.header: ntddk.h
req.include-header: wdm.h
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: FILE_FS_FULL_SIZE_INFORMATION_EX, *PFILE_FS_FULL_SIZE_INFORMATION_EX
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- ntddk.h
api_name: 
- _FILE_FS_FULL_SIZE_INFORMATION_EX
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# _FILE_FS_FULL_SIZE_INFORMATION_EX structure

## -description
Used in a request to query sector size information for a file system volume.

## -struct-fields

### -field ActualTotalAllocationUnits
Total space (in clusters) on the volume without considering the quota setting.
  
### -field ActualAvailableAllocationUnits
Total space available (in clusters) on the volume (in clusters) without considering the quota setting.
 
### -field ActualPoolUnavailableAllocationUnits
Total unavailable space (in clusters) for the volume due to insufficient free pool space indicated by **PoolAvailableAllocationUnits**.

### -field CallerTotalAllocationUnits
Total space (in clusters) on the volume including available, unavailable, used, and reserved space.

### -field CallerAvailableAllocationUnits
Total space (in clusters) on the volume that is available to the user associated with the calling thread.
 
### -field CallerPoolUnavailableAllocationUnits
Total space (in clusters) that is the unavailable space for the volume due to insufficient free pool space.
 
### -field UsedAllocationUnits
Total used space (in clusters) on the volume.
 
### -field TotalReservedAllocationUnits
Total reserved space (in clusters) on the volume.
 
### -field VolumeStorageReserveAllocationUnits
A special type of reserved space (in clusters) for per-volume storage reserve. This value is included in **TotalReservedAllocationUnits**.
 
### -field AvailableCommittedAllocationUnits
Total space (in clusters) that has been committed by storage pool but has not been allocated by file system.
 
### -field PoolAvailableAllocationUnits
Total available space (in clusters) in corresponding storage pool. If the volume is not a spaces volume, the **PoolAvailableAllocationUnits** is set to zero.
 
### -field SectorsPerAllocationUnit
Number of sectors in each allocation unit.
 
### -field BytesPerSector
Number of bytes in each sector. 

## -remarks
This information can be queried in either of the following ways: 

- Call [**FltQueryVolumeInformation**](../fltkernel/nf-fltkernel-fltqueryvolumeinformation.md) or [**ZwQueryVolumeInformationFile**](../ntifs/nf-ntifs-ntqueryvolumeinformationfile.md), passing FileFsFullSizeInformationEx as the value of _FileInformationClass_ and passing a caller-allocated, **FILE_FS_FULL_SIZE_INFORMATION_EX**-structured buffer as the value of FileInformation.

- Create an IRP with major function code IRP_MJ_QUERY_VOLUME_INFORMATION.

No specific access rights are required to query this information. Thus this information is available as long as the volume is accessed through an open handle to the volume itself, or to a file or directory on the volume.

The size of the buffer passed in the _FileInformation_ parameter to [**FltQueryVolumeInformation**](../fltkernel/nf-fltkernel-fltqueryvolumeinformation.md) or [**ZwQueryVolumeInformationFile**](../ntifs/nf-ntifs-ntqueryvolumeinformationfile.md) must be at least sizeof (FILE_FS_FULL_SIZE_INFORMATION_EX). 

This structure must be aligned on a LONGLONG (8-byte) boundary.


## -see-also
[**FltQueryVolumeInformation**](../fltkernel/nf-fltkernel-fltqueryvolumeinformation.md) 

[**ZwQueryVolumeInformationFile**](../ntifs/nf-ntifs-ntqueryvolumeinformationfile.md)
