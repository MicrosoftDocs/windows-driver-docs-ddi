---
UID: NS:ntddstor._GET_MEDIA_TYPES
title: _GET_MEDIA_TYPES (ntddstor.h)
description: The GET_MEDIA_TYPES structure is used in conjunction with the IOCTL_STORAGE_GET_MEDIA_TYPES_EX request to retrieve information about the types of media supported by a device.
old-location: storage\get_media_types.htm
tech.root: storage
ms.assetid: e803505f-37a0-4b20-bd6f-ce0f79eead03
ms.date: 03/29/2018
keywords: ["_GET_MEDIA_TYPES structure"]
ms.keywords: "*PGET_MEDIA_TYPES, GET_MEDIA_TYPES, GET_MEDIA_TYPES structure [Storage Devices], PGET_MEDIA_TYPES, PGET_MEDIA_TYPES structure pointer [Storage Devices], _GET_MEDIA_TYPES, ntddstor/GET_MEDIA_TYPES, ntddstor/PGET_MEDIA_TYPES, storage.get_media_types, structs-general_68f75a58-b2a5-4d6a-b9ba-0019e36034ef.xml"
f1_keywords:
 - "ntddstor/GET_MEDIA_TYPES"
 - "GET_MEDIA_TYPES"
req.header: ntddstor.h
req.include-header: Ntddstor.h, Minitape.h
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
- GET_MEDIA_TYPES
product:
- Windows
targetos: Windows
req.typenames: GET_MEDIA_TYPES, *PGET_MEDIA_TYPES
---

# _GET_MEDIA_TYPES structure


## -description


The GET_MEDIA_TYPES structure is used in conjunction with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_get_media_types_ex">IOCTL_STORAGE_GET_MEDIA_TYPES_EX</a> request to retrieve information about the types of media supported by a device. 


## -struct-fields




### -field DeviceType

Specifies one of the system-defined FILE_DEVICE_<i>XXX</i> constants indicating the type of device (such as FILE_DEVICE_DISK, FILE_DEVICE_KEYBOARD, and so forth) or a vendor-defined value for a new type of device. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/specifying-device-types">Specifying Device Types</a>. 


### -field MediaInfoCount

Contains the number of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_device_media_info">DEVICE_MEDIA_INFO</a> structures in the array starting at <b>MediaInfo</b>.


### -field MediaInfo

Contains an array whose first element holds the first DEVICE_MEDIA_INFO structure in the array.


## -remarks



A storage class driver must handle the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_get_media_types_ex">IOCTL_STORAGE_GET_MEDIA_TYPES_EX</a> request to support any device that the Removable Storage Manager (RSM) accesses, whether the device is a stand-alone device or a data transfer element (drive) in a media library or changer. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_device_media_info">DEVICE_MEDIA_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_get_media_types_ex">IOCTL_STORAGE_GET_MEDIA_TYPES_EX</a>
 

 

