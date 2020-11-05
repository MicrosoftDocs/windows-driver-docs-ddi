---
UID: NS:ntddstor._STORAGE_RPMB_DESCRIPTOR
title: STORAGE_RPMB_DESCRIPTOR
ms.date: 10/28/2020
ms.assetid: 6f92b790-937c-4cb6-9db2-5a9ddc3e738b
tech.root: storage
ms.topic: language-reference
targetos: Windows
description: The STORAGE_RPMB_DESCRIPTOR structure contains information about a device's Replay Protected Memory Block (RPMB) support.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntddstor.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: STORAGE_RPMB_DESCRIPTOR, *PSTORAGE_RPMB_DESCRIPTOR
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _STORAGE_RPMB_DESCRIPTOR
 - PSTORAGE_RPMB_DESCRIPTOR
 - STORAGE_RPMB_DESCRIPTOR
f1_keywords:
 - _STORAGE_RPMB_DESCRIPTOR
 - ntddstor/_STORAGE_RPMB_DESCRIPTOR
 - PSTORAGE_RPMB_DESCRIPTOR
 - ntddstor/PSTORAGE_RPMB_DESCRIPTOR
 - STORAGE_RPMB_DESCRIPTOR
 - ntddstor/STORAGE_RPMB_DESCRIPTOR
dev_langs:
 - c++
---

## -description

The **STORAGE_RPMB_DESCRIPTOR** structure contains information about a device's Replay Protected Memory Block (RPMB) support.

## -struct-fields

### -field Version

Version of this structure. Set to STORAGE_RPMB_DESCRIPTOR_VERSION_1.

### -field Size

Size of this structure, in bytes. Set to ```sizeof(STORAGE_RPMB_DESCRIPTOR)```.

### -field SizeInBytes

Size of the RPMB, in bytes. **SizeInBytes** cannot be zero.

### -field MaxReliableWriteSizeInBytes

Maximum amount of data supported in one transaction, in bytes. **MaxReliableWriteSizeInBytes** cannot be zero.

### -field FrameFormat

A [**STORAGE_RPMB_FRAME_TYPE](ns-ntddstor-storage_rpmb_data_frame.md) structure identifying the frame format that the payload will be in.

## -remarks

An application will issue [**IOCTL_STORAGE_QUERY_PROPERTY**](ni-ntddstor-ioctl_storage_query_property.md) with the [**STORAGE_PROPERTY_ID**](ne-ntddstor-storage_property_id.md) enumeration set to **StorageAdapterRpmbProperty** to determine whether the device contains an RPMB, and the maximum payload size the RPMB supports.

Storport responds with the payload information in this structure when the [**STORAGE_QUERY_TYPE**](ne-ntddstor-_storage_query_type.md) enumeration is set to **PropertyStandardQuery**.

## -see-also

[**IOCTL_STORAGE_QUERY_PROPERTY**](ni-ntddstor-ioctl_storage_query_property.md)

[**STORAGE_PROPERTY_ID**](ne-ntddstor-storage_property_id.md)

[**STORAGE_QUERY_TYPE**](ne-ntddstor-_storage_query_type.md)

[**STORAGE_RPMB_FRAME_TYPE](ns-ntddstor-storage_rpmb_data_frame.md)
