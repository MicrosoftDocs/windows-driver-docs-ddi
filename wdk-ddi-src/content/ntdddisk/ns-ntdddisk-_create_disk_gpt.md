---
UID: NS:ntdddisk._CREATE_DISK_GPT
title: _CREATE_DISK_GPT (ntdddisk.h)
description: The CREATE_DISK_GPT structure is used with the IOCTL IOCTL_DISK_CREATE_DISK to initialize a disk with an empty GPT partition table.
old-location: storage\create_disk_gpt.htm
tech.root: storage
ms.assetid: 24ae7329-064f-43bf-8c1d-8aad9fdf2254
ms.date: 03/29/2018
ms.keywords: "*PCREATE_DISK_GPT, CREATE_DISK_GPT, CREATE_DISK_GPT structure [Storage Devices], PCREATE_DISK_GPT, PCREATE_DISK_GPT structure pointer [Storage Devices], _CREATE_DISK_GPT, ntdddisk/CREATE_DISK_GPT, ntdddisk/PCREATE_DISK_GPT, storage.create_disk_gpt, structs-disk_c5c62f65-c252-482b-bbf7-1bb021920649.xml"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntdddisk.h
api_name:
- CREATE_DISK_GPT
product:
- Windows
targetos: Windows
req.typenames: CREATE_DISK_GPT, *PCREATE_DISK_GPT
---

# _CREATE_DISK_GPT structure


## -description


The CREATE_DISK_GPT structure is used with the IOCTL <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntdddisk/ni-ntdddisk-ioctl_disk_create_disk">IOCTL_DISK_CREATE_DISK</a> to initialize a disk with an empty GPT partition table.


## -struct-fields




### -field DiskId

Specifies the GUID that uniquely identifies the disk.


### -field MaxPartitionCount

Specifies the maximum number of partitions allowed on the disk.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntdddisk/ns-ntdddisk-_create_disk">CREATE_DISK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntdddisk/ni-ntdddisk-ioctl_disk_create_disk">IOCTL_DISK_CREATE_DISK</a>
 

 

