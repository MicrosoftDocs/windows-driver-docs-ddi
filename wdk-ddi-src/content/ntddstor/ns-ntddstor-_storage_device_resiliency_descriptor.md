---
UID: NS:ntddstor._STORAGE_DEVICE_RESILIENCY_DESCRIPTOR
title: _STORAGE_DEVICE_RESILIENCY_DESCRIPTOR (ntddstor.h)
description: Reserved for system use.
old-location: storage\storage_device_resiliency_descriptor.htm
tech.root: storage
ms.assetid: 71351CB7-1295-4797-802C-23A6B1C2C53F
ms.date: 03/29/2018
keywords: ["STORAGE_DEVICE_RESILIENCY_DESCRIPTOR structure"]
ms.keywords: PSTORAGE_DEVICE_RESILIENCY_DESCRIPTOR, PSTORAGE_DEVICE_RESILIENCY_DESCRIPTOR structure pointer [Storage Devices], STORAGE_DEVICE_RESILIENCY_DESCRIPTOR, STORAGE_DEVICE_RESILIENCY_DESCRIPTOR structure [Storage Devices], _STORAGE_DEVICE_RESILIENCY_DESCRIPTOR, ntddstor/PSTORAGE_DEVICE_RESILIENCY_DESCRIPTOR, ntddstor/STORAGE_DEVICE_RESILIENCY_DESCRIPTOR, storage.storage_device_resiliency_descriptor
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.typenames: STORAGE_DEVICE_RESILIENCY_DESCRIPTOR, PSTORAGE_DEVICE_RESILIENCY_DESCRIPTOR
f1_keywords:
 - _STORAGE_DEVICE_RESILIENCY_DESCRIPTOR
 - ntddstor/_STORAGE_DEVICE_RESILIENCY_DESCRIPTOR
 - PSTORAGE_DEVICE_RESILIENCY_DESCRIPTOR
 - ntddstor/PSTORAGE_DEVICE_RESILIENCY_DESCRIPTOR
 - STORAGE_DEVICE_RESILIENCY_DESCRIPTOR
 - ntddstor/STORAGE_DEVICE_RESILIENCY_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - STORAGE_DEVICE_RESILIENCY_DESCRIPTOR
---

# _STORAGE_DEVICE_RESILIENCY_DESCRIPTOR structure


## -description

Reserved for system use.

## -struct-fields

### -field Version

Contains the size of this structure, in bytes. The value of this member will change as members are added to 
      the structure. Set to 
      <code>sizeof(STORAGE_DEVICE_RESILIENCY_DESCRIPTOR)</code>.

### -field Size

Specifies the total size of the data returned, in bytes. This may include data that follows this 
      structure.

### -field NameOffset

Byte offset to the null-terminated ASCII string containing the resiliency properties Name. For devices with 
      no Name property, this will be zero.

### -field NumberOfLogicalCopies

Number of logical copies of data that are available.

### -field NumberOfPhysicalCopies

Number of complete copies of data that are stored.

### -field PhysicalDiskRedundancy

Number of disks that can fail without leading to data loss.

### -field NumberOfColumns

Number of columns in the storage device.

### -field Interleave

Size of a stripe unit of the storage device, in bytes. This is also referred to as the stripe width or 
      interleave of the storage device.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a>

