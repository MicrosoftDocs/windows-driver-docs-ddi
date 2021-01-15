---
UID: NS:ntdddisk._CREATE_DISK_MBR
title: _CREATE_DISK_MBR (ntdddisk.h)
description: The CREATE_DISK_MBR structure is used with the IOCTL IOCTL_DISK_CREATE_DISK to initialize a disk with an empty MBR partition table.
old-location: storage\create_disk_mbr.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["CREATE_DISK_MBR structure"]
ms.keywords: "*PCREATE_DISK_MBR, CREATE_DISK_MBR, CREATE_DISK_MBR structure [Storage Devices], PCREATE_DISK_MBR, PCREATE_DISK_MBR structure pointer [Storage Devices], _CREATE_DISK_MBR, ntdddisk/CREATE_DISK_MBR, ntdddisk/PCREATE_DISK_MBR, storage.create_disk_mbr, structs-disk_680fcaf9-080c-4e38-be53-ed9899539d9b.xml"
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
targetos: Windows
req.typenames: CREATE_DISK_MBR, *PCREATE_DISK_MBR
f1_keywords:
 - _CREATE_DISK_MBR
 - ntdddisk/_CREATE_DISK_MBR
 - PCREATE_DISK_MBR
 - ntdddisk/PCREATE_DISK_MBR
 - CREATE_DISK_MBR
 - ntdddisk/CREATE_DISK_MBR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntdddisk.h
api_name:
 - _CREATE_DISK_MBR
 - PCREATE_DISK_MBR
 - CREATE_DISK_MBR
---

# _CREATE_DISK_MBR structure


## -description

The CREATE_DISK_MBR structure is used with the IOCTL <a href="/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_create_disk">IOCTL_DISK_CREATE_DISK</a> to initialize a disk with an empty MBR partition table.

## -struct-fields

### -field Signature

Specifies the disk signature value, which uniquely identifies the disk.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_create_disk">CREATE_DISK</a>



<a href="/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_create_disk">IOCTL_DISK_CREATE_DISK</a>

