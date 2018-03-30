---
UID: NS:ntdddisk._CREATE_DISK_GPT
title: "_CREATE_DISK_GPT"
author: windows-driver-content
description: The CREATE_DISK_GPT structure is used with the IOCTL IOCTL_DISK_CREATE_DISK to initialize a disk with an empty GPT partition table.
old-location: storage\create_disk_gpt.htm
old-project: storage
ms.assetid: 24ae7329-064f-43bf-8c1d-8aad9fdf2254
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PCREATE_DISK_GPT, CREATE_DISK_GPT, CREATE_DISK_GPT structure [Storage Devices], PCREATE_DISK_GPT, PCREATE_DISK_GPT structure pointer [Storage Devices], _CREATE_DISK_GPT, ntdddisk/CREATE_DISK_GPT, ntdddisk/PCREATE_DISK_GPT, storage.create_disk_gpt, structs-disk_c5c62f65-c252-482b-bbf7-1bb021920649.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntdddisk.h
api_name:
-	CREATE_DISK_GPT
product: Windows
targetos: Windows
req.typenames: CREATE_DISK_GPT, *PCREATE_DISK_GPT
---

# _CREATE_DISK_GPT structure


## -description


The CREATE_DISK_GPT structure is used with the IOCTL <a href="https://msdn.microsoft.com/library/windows/hardware/ff559436">IOCTL_DISK_CREATE_DISK</a> to initialize a disk with an empty GPT partition table.


## -struct-fields




### -field DiskId

Specifies the GUID that uniquely identifies the disk.


### -field MaxPartitionCount

Specifies the maximum number of partitions allowed on the disk.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552484">CREATE_DISK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559436">IOCTL_DISK_CREATE_DISK</a>
 

 

