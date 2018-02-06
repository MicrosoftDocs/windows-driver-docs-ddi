---
UID: NS:ntdddisk._CREATE_DISK_MBR
title: "_CREATE_DISK_MBR"
author: windows-driver-content
description: The CREATE_DISK_MBR structure is used with the IOCTL IOCTL_DISK_CREATE_DISK to initialize a disk with an empty MBR partition table.
old-location: storage\create_disk_mbr.htm
old-project: storage
ms.assetid: afc0e705-ae98-486b-82d3-4f21fca89e70
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: CREATE_DISK_MBR, _CREATE_DISK_MBR, *PCREATE_DISK_MBR, ntdddisk/PCREATE_DISK_MBR, storage.create_disk_mbr, PCREATE_DISK_MBR, PCREATE_DISK_MBR structure pointer [Storage Devices], CREATE_DISK_MBR structure [Storage Devices], ntdddisk/CREATE_DISK_MBR, structs-disk_680fcaf9-080c-4e38-be53-ed9899539d9b.xml
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
-	CREATE_DISK_MBR
product: Windows
targetos: Windows
req.typenames: CREATE_DISK_MBR, *PCREATE_DISK_MBR
---

# _CREATE_DISK_MBR structure


## -description


The CREATE_DISK_MBR structure is used with the IOCTL <a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_create_disk.md">IOCTL_DISK_CREATE_DISK</a> to initialize a disk with an empty MBR partition table.


## -syntax


````
typedef struct _CREATE_DISK_MBR {
  ULONG Signature;
} CREATE_DISK_MBR, *PCREATE_DISK_MBR;
````


## -struct-fields




### -field Signature

Specifies the disk signature value, which uniquely identifies the disk.


## -see-also

<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_create_disk.md">IOCTL_DISK_CREATE_DISK</a>

<a href="..\ntdddisk\ns-ntdddisk-_create_disk.md">CREATE_DISK</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CREATE_DISK_MBR structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

