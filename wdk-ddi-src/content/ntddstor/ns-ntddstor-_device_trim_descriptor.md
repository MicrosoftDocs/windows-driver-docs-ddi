---
UID: NS:ntddstor._DEVICE_TRIM_DESCRIPTOR
title: _DEVICE_TRIM_DESCRIPTOR (ntddstor.h)
description: The DEVICE_TRIM_DESCRIPTOR structure is used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY request to retrieve the trim descriptor data for a device.
old-location: storage\device_trim_descriptor.htm
tech.root: storage
ms.assetid: e36bca55-63d0-41ef-83b9-8f0cfd450323
ms.date: 03/29/2018
ms.keywords: "*PDEVICE_TRIM_DESCRIPTOR, DEVICE_TRIM_DESCRIPTOR, DEVICE_TRIM_DESCRIPTOR structure [Storage Devices], PDEVICE_TRIM_DESCRIPTOR, PDEVICE_TRIM_DESCRIPTOR structure pointer [Storage Devices], _DEVICE_TRIM_DESCRIPTOR, ntddstor/DEVICE_TRIM_DESCRIPTOR, ntddstor/PDEVICE_TRIM_DESCRIPTOR, storage.device_trim_descriptor, structs-general_eeaa452e-bc49-47ac-9d6f-4a7bbc022b2f.xml"
ms.topic: struct
f1_keywords:
 - "ntddstor/DEVICE_TRIM_DESCRIPTOR"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddstor.h
api_name:
- DEVICE_TRIM_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: DEVICE_TRIM_DESCRIPTOR, *PDEVICE_TRIM_DESCRIPTOR
---

# _DEVICE_TRIM_DESCRIPTOR structure


## -description


The DEVICE_TRIM_DESCRIPTOR structure is used in conjunction with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a> request to retrieve the trim descriptor data for a device.


## -struct-fields




### -field Version

Contains the size of the structure DEVICE_TRIM_DESCRIPTOR. The value of this member will change as members are added to the structure.


### -field Size

Specifies the total size of the descriptor, in bytes.


### -field TrimEnabled

Specifies whether trim is enabled for the device.


## -remarks



Storage class drivers issue a device-control request with the I/O control code  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a> to retrieve this structure, which contains trim information for the device. The structure can be retrieved either from the device object for the bus or from an FDO, which forwards the request to the underlying bus.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a>
 

 

