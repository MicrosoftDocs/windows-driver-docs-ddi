---
UID: NS:ntddstor._DEVICE_COPY_OFFLOAD_DESCRIPTOR
title: _DEVICE_COPY_OFFLOAD_DESCRIPTOR (ntddstor.h)
description: Used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY request to describe the copy offload capabilities of a storage device.
old-location: storage\device_copy_offload_descriptor.htm
tech.root: storage
ms.assetid: 192684D1-3D01-4EAA-989F-2E21E7187B3B
ms.date: 03/29/2018
keywords: ["_DEVICE_COPY_OFFLOAD_DESCRIPTOR structure"]
ms.keywords: "*PDEVICE_COPY_OFFLOAD_DESCRIPTOR, DEVICE_COPY_OFFLOAD_DESCRIPTOR, DEVICE_COPY_OFFLOAD_DESCRIPTOR structure [Storage Devices], PDEVICE_COPY_OFFLOAD_DESCRIPTOR, PDEVICE_COPY_OFFLOAD_DESCRIPTOR structure pointer [Storage Devices], _DEVICE_COPY_OFFLOAD_DESCRIPTOR, ntddstor/DEVICE_COPY_OFFLOAD_DESCRIPTOR, ntddstor/PDEVICE_COPY_OFFLOAD_DESCRIPTOR, storage.device_copy_offload_descriptor"
f1_keywords:
 - "ntddstor/DEVICE_COPY_OFFLOAD_DESCRIPTOR"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddstor.h
api_name:
- DEVICE_COPY_OFFLOAD_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: DEVICE_COPY_OFFLOAD_DESCRIPTOR, *PDEVICE_COPY_OFFLOAD_DESCRIPTOR
---

# _DEVICE_COPY_OFFLOAD_DESCRIPTOR structure


## -description


Used in conjunction with the 
   <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a> request to describe the copy offload capabilities of a storage device.


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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a>
 

 

