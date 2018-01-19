---
UID: NS:ntdddisk._CREATE_DISK
title: _CREATE_DISK
author: windows-driver-content
description: The CREATE_DISK structure is used with the IOCTL_DISK_CREATE_DISK IOCTL to initialize a disk with an empty partition table. The partition table styles are master boot record (MBR) or GUID partition table (GPT).
old-location: storage\create_disk.htm
old-project: storage
ms.assetid: 20989831-5ff0-4457-9dae-ceaf34830a2e
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _CREATE_DISK, *PCREATE_DISK, CREATE_DISK
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
req.alt-api: CREATE_DISK
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
req.typenames: *PCREATE_DISK, CREATE_DISK
---

# _CREATE_DISK structure



## -description
The CREATE_DISK structure is used with the  <a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_create_disk.md">IOCTL_DISK_CREATE_DISK</a>  IOCTL to initialize a disk with an empty partition table. The partition table styles are master boot record (MBR)  or GUID partition table (GPT).



## -syntax

````
typedef struct _CREATE_DISK {
  PARTITION_STYLE PartitionStyle;
  union {
    CREATE_DISK_MBR Mbr;
    CREATE_DISK_GPT Gpt;
  };
} CREATE_DISK, *PCREATE_DISK;
````


## -struct-fields

### -field PartitionStyle

Takes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563773">PARTITION_STYLE</a> enumerated value that specifies the type of partition table to use when formatting the disk.


### -field Mbr

Contains the signature used to initialize an MBR-style disk partition for the first time. This member is valid when <b>PartitionStyle</b> is PARTITION_STYLE_MBR. For more information, see <a href="..\ntdddisk\ns-ntdddisk-_create_disk_mbr.md">CREATE_DISK_MBR</a>.


### -field Gpt

Contains data used to initialize a GPT-style disk partition for the first time. This member is valid when <b>PartitionStyle</b> is PARTITION_STYLE_GPT. For more information, see <a href="..\ntdddisk\ns-ntdddisk-_create_disk_gpt.md">CREATE_DISK_GPT</a>. 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_create_disk.md">IOCTL_DISK_CREATE_DISK</a>
</dt>
<dt>
<a href="..\ntdddisk\ns-ntdddisk-_create_disk_mbr.md">CREATE_DISK_MBR</a>
</dt>
<dt>
<a href="..\ntdddisk\ns-ntdddisk-_create_disk_gpt.md">CREATE_DISK_GPT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563773">PARTITION_STYLE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CREATE_DISK structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

