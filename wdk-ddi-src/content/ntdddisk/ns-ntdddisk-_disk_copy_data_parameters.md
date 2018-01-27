---
UID: NS:ntdddisk._DISK_COPY_DATA_PARAMETERS
title: _DISK_COPY_DATA_PARAMETERS
author: windows-driver-content
description: DISK_COPY_DATA_PARAMETERS is used with IOCTL_DISK_COPY_DATA to copy data from one area of the disk to another.
old-location: storage\disk_copy_data_parameters.htm
old-project: storage
ms.assetid: 17d75b0e-2521-441f-99ea-75d2ea1d52b3
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ntdddisk/PDISK_COPY_DATA_PARAMETERS, DISK_COPY_DATA_PARAMETERS structure [Storage Devices], structs-disk_3b1d751a-57a0-47a6-accd-f895fdb9bb61.xml, storage.disk_copy_data_parameters, DISK_COPY_DATA_PARAMETERS, PDISK_COPY_DATA_PARAMETERS structure pointer [Storage Devices], *PDISK_COPY_DATA_PARAMETERS, ntdddisk/DISK_COPY_DATA_PARAMETERS, PDISK_COPY_DATA_PARAMETERS, _DISK_COPY_DATA_PARAMETERS
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	ntdddisk.h
apiname: 
-	DISK_COPY_DATA_PARAMETERS
product: Windows
targetos: Windows
req.typenames: *PDISK_COPY_DATA_PARAMETERS, DISK_COPY_DATA_PARAMETERS
---

# _DISK_COPY_DATA_PARAMETERS structure


## -description


DISK_COPY_DATA_PARAMETERS is used with IOCTL_DISK_COPY_DATA to copy data from one area of the disk to another.


## -syntax


````
typedef struct _DISK_COPY_DATA_PARAMETERS {
  LARGE_INTEGER SourceOffset;
  LARGE_INTEGER DestinationOffset;
  LARGE_INTEGER CopyLength;
  ULONGLONG     Reserved;
} DISK_COPY_DATA_PARAMETERS, *PDISK_COPY_DATA_PARAMETERS;
````


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

<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_copy_data.md">IOCTL_DISK_COPY_DATA</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DISK_COPY_DATA_PARAMETERS structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

