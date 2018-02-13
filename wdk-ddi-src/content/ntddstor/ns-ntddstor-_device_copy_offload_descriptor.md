---
UID: NS:ntddstor._DEVICE_COPY_OFFLOAD_DESCRIPTOR
title: "_DEVICE_COPY_OFFLOAD_DESCRIPTOR"
author: windows-driver-content
description: Used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY request to describe the copy offload capabilities of a storage device.
old-location: storage\device_copy_offload_descriptor.htm
old-project: storage
ms.assetid: 192684D1-3D01-4EAA-989F-2E21E7187B3B
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ntddstor/DEVICE_COPY_OFFLOAD_DESCRIPTOR, _DEVICE_COPY_OFFLOAD_DESCRIPTOR, DEVICE_COPY_OFFLOAD_DESCRIPTOR structure [Storage Devices], PDEVICE_COPY_OFFLOAD_DESCRIPTOR structure pointer [Storage Devices], PDEVICE_COPY_OFFLOAD_DESCRIPTOR, *PDEVICE_COPY_OFFLOAD_DESCRIPTOR, DEVICE_COPY_OFFLOAD_DESCRIPTOR, ntddstor/PDEVICE_COPY_OFFLOAD_DESCRIPTOR, storage.device_copy_offload_descriptor
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
-	DEVICE_COPY_OFFLOAD_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: DEVICE_COPY_OFFLOAD_DESCRIPTOR, *PDEVICE_COPY_OFFLOAD_DESCRIPTOR
---

# _DEVICE_COPY_OFFLOAD_DESCRIPTOR structure


## -description


Used in conjunction with the 
   <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> request to describe the copy offload capabilities of a storage device.


## -syntax


````
typedef struct _DEVICE_COPY_OFFLOAD_DESCRIPTOR {
  ULONG      Version;
  ULONG      Size;
  ULONG      MaximumTokenLifetime;
  ULONG      DefaultTokenLifetime;
  ULONGULONG MaximumTransferSize;
  ULONGULONG OptimalTransferCount;
  ULONG      MaximumDataDescriptors;
  ULONG      MaximumTransferLengthPerDescriptor;
  ULONG      OptimalTransferLengthPerDescriptor;
  USHORT     OptimalTransferLengthGranularity;
  UCHAR      Reserved[2];
} DEVICE_COPY_OFFLOAD_DESCRIPTOR, *PDEVICE_COPY_OFFLOAD_DESCRIPTOR;
````


## -struct-fields




### -field Version

Contains the size of this structure, in bytes. The value of this member will change as members are added to 
      the structure.


### -field Size

Specifies the total size of the data returned, in bytes. This may include data that follows this 
      structure.


### -field MaximumTokenLifetime

The maximum lifetime of the token, in seconds.


### -field DefaultTokenLifetime

The default lifetime of the token, in seconds.


### -field MaximumTransferSize

The maximum transfer size, in bytes.


### -field OptimalTransferCount

The optimal transfer size, in bytes.


### -field MaximumDataDescriptors

The maximum number of data descriptors.


### -field MaximumTransferLengthPerDescriptor

The maximum transfer length, in blocks, per descriptor.


### -field OptimalTransferLengthPerDescriptor

The optimal transfer length, in blocks, per descriptor.


### -field OptimalTransferLengthGranularity

The granularity of the optimal transfer length, in blocks. Transfer lengths that are not an even multiple 
      of this length may be delayed.


### -field Reserved

Reserved for future use.


## -see-also

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DEVICE_COPY_OFFLOAD_DESCRIPTOR structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

