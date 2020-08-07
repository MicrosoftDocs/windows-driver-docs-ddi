---
UID: NS:ntdddisk._DISK_COPY_DATA_PARAMETERS
title: _DISK_COPY_DATA_PARAMETERS (ntdddisk.h)
description: DISK_COPY_DATA_PARAMETERS is used with IOCTL_DISK_COPY_DATA to copy data from one area of the disk to another.
old-location: storage\disk_copy_data_parameters.htm
tech.root: storage
ms.assetid: 17d75b0e-2521-441f-99ea-75d2ea1d52b3
ms.date: 03/29/2018
keywords: ["DISK_COPY_DATA_PARAMETERS structure"]
ms.keywords: "*PDISK_COPY_DATA_PARAMETERS, DISK_COPY_DATA_PARAMETERS, DISK_COPY_DATA_PARAMETERS structure [Storage Devices], PDISK_COPY_DATA_PARAMETERS, PDISK_COPY_DATA_PARAMETERS structure pointer [Storage Devices], _DISK_COPY_DATA_PARAMETERS, ntdddisk/DISK_COPY_DATA_PARAMETERS, ntdddisk/PDISK_COPY_DATA_PARAMETERS, storage.disk_copy_data_parameters, structs-disk_3b1d751a-57a0-47a6-accd-f895fdb9bb61.xml"
f1_keywords:
 - "ntdddisk/DISK_COPY_DATA_PARAMETERS"
 - "DISK_COPY_DATA_PARAMETERS"
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
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
- ntdddisk.h
api_name:
- DISK_COPY_DATA_PARAMETERS
targetos: Windows
req.typenames: DISK_COPY_DATA_PARAMETERS, *PDISK_COPY_DATA_PARAMETERS
---

# _DISK_COPY_DATA_PARAMETERS structure


## -description


DISK_COPY_DATA_PARAMETERS is used with IOCTL_DISK_COPY_DATA to copy data from one area of the disk to another.


## -struct-fields




### -field SourceOffset

Contains the byte offset of the source for the copy. This number must be sector-aligned.


### -field DestinationOffset

Contains the byte offset of the destination of the copy. This number must be sector-aligned.


### -field CopyLength

Contains the number of bytes to copy. This number must be sector-aligned.


### -field Reserved

Must be zero.


## -remarks



The source and destination areas must not overlap.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_copy_data">IOCTL_DISK_COPY_DATA</a>
 

 

