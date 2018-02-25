---
UID: NS:ntdddisk._CREATE_DISK_GPT
title: "_CREATE_DISK_GPT"
author: windows-driver-content
description: The CREATE_DISK_GPT structure is used with the IOCTL IOCTL_DISK_CREATE_DISK to initialize a disk with an empty GPT partition table.
old-location: storage\create_disk_gpt.htm
old-project: storage
ms.assetid: 24ae7329-064f-43bf-8c1d-8aad9fdf2254
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PCREATE_DISK_GPT, ,, A, C, CREATE_DISK_GPT, CREATE_DISK_GPT structure [Storage Devices], D, E, G, I, K, P, PCREATE_DISK_GPT, PCREATE_DISK_GPT structure pointer [Storage Devices], R, S, T, _, _CREATE_DISK_GPT, ntdddisk/CREATE_DISK_GPT, ntdddisk/PCREATE_DISK_GPT, storage.create_disk_gpt, structs-disk_c5c62f65-c252-482b-bbf7-1bb021920649.xml"
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
-	CREATE_DISK_GPT
product: Windows
targetos: Windows
req.typenames: CREATE_DISK_GPT, *PCREATE_DISK_GPT
---

# _CREATE_DISK_GPT structure


## -description


The CREATE_DISK_GPT structure is used with the IOCTL <a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_create_disk.md">IOCTL_DISK_CREATE_DISK</a> to initialize a disk with an empty GPT partition table.


## -syntax


````
typedef struct _CREATE_DISK_GPT {
  GUID  DiskId;
  ULONG MaxPartitionCount;
} CREATE_DISK_GPT, *PCREATE_DISK_GPT;
````


## -struct-fields




### -field DiskId

Specifies the GUID that uniquely identifies the disk.


### -field MaxPartitionCount

Specifies the maximum number of partitions allowed on the disk.


## -see-also

<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_create_disk.md">IOCTL_DISK_CREATE_DISK</a>



<a href="..\ntdddisk\ns-ntdddisk-_create_disk.md">CREATE_DISK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CREATE_DISK_GPT structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

