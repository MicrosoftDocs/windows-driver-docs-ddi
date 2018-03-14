---
UID: NS:ntddstor._DEVICE_SEEK_PENALTY_DESCRIPTOR
title: "_DEVICE_SEEK_PENALTY_DESCRIPTOR"
author: windows-driver-content
description: The DEVICE_SEEK_PENALTY_DESCRIPTOR structure is used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY request to retrieve the seek penalty descriptor data for a device.
old-location: storage\device_seek_penalty_descriptor.htm
old-project: storage
ms.assetid: c12b66a4-fdb5-40d3-a767-c15477391179
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PDEVICE_SEEK_PENALTY_DESCRIPTOR, DEVICE_SEEK_PENALTY_DESCRIPTOR, DEVICE_SEEK_PENALTY_DESCRIPTOR structure [Storage Devices], PDEVICE_SEEK_PENALTY_DESCRIPTOR, PDEVICE_SEEK_PENALTY_DESCRIPTOR structure pointer [Storage Devices], _DEVICE_SEEK_PENALTY_DESCRIPTOR, ntddstor/DEVICE_SEEK_PENALTY_DESCRIPTOR, ntddstor/PDEVICE_SEEK_PENALTY_DESCRIPTOR, storage.device_seek_penalty_descriptor, structs-general_9fb189fe-9d56-4460-8860-dc6fe6d2fceb.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
-	ntddstor.h
api_name:
-	DEVICE_SEEK_PENALTY_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: DEVICE_SEEK_PENALTY_DESCRIPTOR, *PDEVICE_SEEK_PENALTY_DESCRIPTOR
---

# _DEVICE_SEEK_PENALTY_DESCRIPTOR structure


## -description


The DEVICE_SEEK_PENALTY_DESCRIPTOR structure is used in conjunction with the <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> request to retrieve the seek penalty descriptor data for a device.


## -syntax


````
typedef struct _DEVICE_SEEK_PENALTY_DESCRIPTOR {
  ULONG   Version;
  ULONG   Size;
  BOOLEAN IncursSeekPenalty;
} DEVICE_SEEK_PENALTY_DESCRIPTOR, *PDEVICE_SEEK_PENALTY_DESCRIPTOR;
````


## -struct-fields




### -field Version

Contains the size of the structure DEVICE_SEEK_PENALTY_DESCRIPTOR. The value of this member will change as members are added to the structure.


### -field Size

Specifies the total size of the descriptor, in bytes.


### -field IncursSeekPenalty

Specifies whether the device incurs a seek penalty.


## -remarks



Storage class drivers issue a device-control request with the I/O control code  <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> to retrieve this structure, which contains seek penalty information for data transfer operations. The structure can be retrieved either from the device object for the bus or from an FDO, which forwards the request to the underlying bus.




## -see-also

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a>



 

 


