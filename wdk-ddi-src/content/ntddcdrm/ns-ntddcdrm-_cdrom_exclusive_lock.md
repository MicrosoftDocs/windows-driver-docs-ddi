---
UID: NS:ntddcdrm._CDROM_EXCLUSIVE_LOCK
title: "_CDROM_EXCLUSIVE_LOCK"
author: windows-driver-content
description: The CDROM_EXCLUSIVE_LOCK structure is used with the IOCTL_CDROM_EXCLUSIVE_ACCESS request to lock a CD-ROM device for exclusive access.
old-location: storage\cdrom_exclusive_lock.htm
old-project: storage
ms.assetid: 8c94cdb2-965a-448c-aa97-f7aae9550662
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PCDROM_EXCLUSIVE_LOCK, CDROM_EXCLUSIVE_LOCK, CDROM_EXCLUSIVE_LOCK structure [Storage Devices], PCDROM_EXCLUSIVE_LOCK, PCDROM_EXCLUSIVE_LOCK structure pointer [Storage Devices], _CDROM_EXCLUSIVE_LOCK, ntddcdrm/CDROM_EXCLUSIVE_LOCK, ntddcdrm/PCDROM_EXCLUSIVE_LOCK, storage.cdrom_exclusive_lock, structs-CD-ROM_98cdead9-8c28-497a-9ba3-f686e87554ea.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
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
-	ntddcdrm.h
api_name:
-	CDROM_EXCLUSIVE_LOCK
product: Windows
targetos: Windows
req.typenames: CDROM_EXCLUSIVE_LOCK, *PCDROM_EXCLUSIVE_LOCK
---

# _CDROM_EXCLUSIVE_LOCK structure


## -description


The CDROM_EXCLUSIVE_LOCK structure is used with the <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_exclusive_access.md">IOCTL_CDROM_EXCLUSIVE_ACCESS</a> request to lock a CD-ROM device for exclusive access.


## -syntax


````
typedef struct _CDROM_EXCLUSIVE_LOCK {
  CDROM_EXCLUSIVE_ACCESS Access;
  UCHAR                  CallerName[CDROM_EXCLUSIVE_CALLER_LENGTH];
} CDROM_EXCLUSIVE_LOCK, *PCDROM_EXCLUSIVE_LOCK;
````


## -struct-fields




### -field Access

A <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_exclusive_access.md">CDROM_EXCLUSIVE_ACCESS</a> structure that specifies the type of exclusive access request and the flags that are associated with the request.


### -field CallerName

A <b>NULL</b>-terminated string that identifies the application or system component that has a lock on the CD-ROM device. The length of the string must be less than or equal to CDROM_EXCLUSIVE_CALLER_LENGTH bytes, including the <b>NULL</b> character at the end of the string. The string must contain alphanumerics (A - Z, a - z, 0 - 9), spaces, periods, commas, colons (:), semi-colons (;), hyphens (-), and underscores (_).


## -see-also

<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_exclusive_access.md">CDROM_EXCLUSIVE_ACCESS</a>



<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_exclusive_access.md">IOCTL_CDROM_EXCLUSIVE_ACCESS</a>



 

 


