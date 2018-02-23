---
UID: NS:ntddstor._STORAGE_DEVICE_RESILIENCY_DESCRIPTOR
title: "_STORAGE_DEVICE_RESILIENCY_DESCRIPTOR"
author: windows-driver-content
description: Reserved for system use.
old-location: storage\storage_device_resiliency_descriptor.htm
old-project: storage
ms.assetid: 71351CB7-1295-4797-802C-23A6B1C2C53F
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: STORAGE_DEVICE_RESILIENCY_DESCRIPTOR, _STORAGE_DEVICE_RESILIENCY_DESCRIPTOR, storage.storage_device_resiliency_descriptor, PSTORAGE_DEVICE_RESILIENCY_DESCRIPTOR, STORAGE_DEVICE_RESILIENCY_DESCRIPTOR structure [Storage Devices], ntddstor/PSTORAGE_DEVICE_RESILIENCY_DESCRIPTOR, PSTORAGE_DEVICE_RESILIENCY_DESCRIPTOR structure pointer [Storage Devices], ntddstor/STORAGE_DEVICE_RESILIENCY_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddstor.h
apiname:
-	STORAGE_DEVICE_RESILIENCY_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: STORAGE_DEVICE_RESILIENCY_DESCRIPTOR, PSTORAGE_DEVICE_RESILIENCY_DESCRIPTOR
---

# _STORAGE_DEVICE_RESILIENCY_DESCRIPTOR structure


## -description


Reserved for system use.


## -syntax


````
typedef struct _STORAGE_DEVICE_RESILIENCY_DESCRIPTOR {
  ULONG Version;
  ULONG Size;
  ULONG NameOffset;
  ULONG NumberOfLogicalCopies;
  ULONG NumberOfPhysicalCopies;
  ULONG PhysicalDiskRedundancy;
  ULONG NumberOfColumns;
  ULONG Interleave;
} STORAGE_DEVICE_RESILIENCY_DESCRIPTOR, *PSTORAGE_DEVICE_RESILIENCY_DESCRIPTOR;
````


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

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_DEVICE_RESILIENCY_DESCRIPTOR structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

