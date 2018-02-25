---
UID: NS:ntddcdvd._DVD_DISK_KEY_DESCRIPTOR
title: "_DVD_DISK_KEY_DESCRIPTOR"
author: windows-driver-content
description: The DVD_DISK_KEY_DESCRIPTOR structure is used in conjunction with the IOCTL_DVD_READ_STRUCTURE request to retrieve a DVD disc key descriptor.
old-location: storage\dvd_disk_key_descriptor.htm
old-project: storage
ms.assetid: 48b0e44d-51bb-48b1-bcbc-6a51fde3c8db
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PDVD_DISK_KEY_DESCRIPTOR, ,, C, D, DVD_DISK_KEY_DESCRIPTOR, DVD_DISK_KEY_DESCRIPTOR structure [Storage Devices], E, I, K, O, P, PDVD_DISK_KEY_DESCRIPTOR, PDVD_DISK_KEY_DESCRIPTOR structure pointer [Storage Devices], R, S, T, V, Y, _, _DVD_DISK_KEY_DESCRIPTOR, ntddcdvd/DVD_DISK_KEY_DESCRIPTOR, ntddcdvd/PDVD_DISK_KEY_DESCRIPTOR, storage.dvd_disk_key_descriptor, structs-DVD_b5c88389-0128-4069-b460-d9fa81a2150e.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddcdvd.h
req.include-header: Ntddcdvd.h
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
-	ntddcdvd.h
apiname:
-	DVD_DISK_KEY_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: DVD_DISK_KEY_DESCRIPTOR, *PDVD_DISK_KEY_DESCRIPTOR
---

# _DVD_DISK_KEY_DESCRIPTOR structure


## -description


The DVD_DISK_KEY_DESCRIPTOR structure is used in conjunction with the <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_dvd_read_structure.md">IOCTL_DVD_READ_STRUCTURE</a> request to retrieve a DVD disc key descriptor. 


## -syntax


````
typedef struct _DVD_DISK_KEY_DESCRIPTOR {
  UCHAR DiskKeyData[2048];
} DVD_DISK_KEY_DESCRIPTOR, *PDVD_DISK_KEY_DESCRIPTOR;
````


## -struct-fields




### -field DiskKeyData

Pointer to a buffer containing the disc key data obfuscated by the bus key.


## -see-also

<a href="..\ntddcdvd\ni-ntddcdvd-ioctl_dvd_read_structure.md">IOCTL_DVD_READ_STRUCTURE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DVD_DISK_KEY_DESCRIPTOR structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

