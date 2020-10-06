---
UID: NS:ntddstor._GET_DEVICE_INTERNAL_STATUS_DATA_REQUEST
title: GET_DEVICE_INTERNAL_STATUS_DATA_REQUEST
description: The GET_DEVICE_INTERNAL_STATUS_DATA_REQUEST structure describes the internal status data being requested through IOCTL_STORAGE_GET_DEVICE_INTERNAL_LOG.
tech.root: storage
ms.assetid: 9370b50a-044b-49dd-9e1a-d946cb825f71
ms.date: 11/30/2019
ms.topic: struct
ms.keywords: GET_DEVICE_INTERNAL_STATUS_DATA_REQUEST, GET_DEVICE_INTERNAL_STATUS_DATA_REQUEST, *PGET_DEVICE_INTERNAL_STATUS_DATA_REQUEST,
req.header: ntddstor.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: GET_DEVICE_INTERNAL_STATUS_DATA_REQUEST, *PGET_DEVICE_INTERNAL_STATUS_DATA_REQUEST
targetos: Windows
f1_keywords:
 - _GET_DEVICE_INTERNAL_STATUS_DATA_REQUEST
 - ntddstor/_GET_DEVICE_INTERNAL_STATUS_DATA_REQUEST
 - PGET_DEVICE_INTERNAL_STATUS_DATA_REQUEST
 - ntddstor/PGET_DEVICE_INTERNAL_STATUS_DATA_REQUEST
 - GET_DEVICE_INTERNAL_STATUS_DATA_REQUEST
 - ntddstor/GET_DEVICE_INTERNAL_STATUS_DATA_REQUEST
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - GET_DEVICE_INTERNAL_STATUS_DATA_REQUEST
product:
 - Windows
---

# GET_DEVICE_INTERNAL_STATUS_DATA_REQUEST structure


## -description

The GET_DEVICE_INTERNAL_STATUS_DATA_REQUEST structure describes the internal status data being requested through [IOCTL_STORAGE_GET_DEVICE_INTERNAL_LOG](ni-ntddstor-ioctl_storage_get_device_internal_log.md).

## -struct-fields

### -field Version

Version of this structure. Set to **sizeof**(GET_DEVICE_INTERNAL_STATUS_DATA_REQUEST).

### -field Size

Total size in bytes of this structure. Set to **sizeof**(GET_DEVICE_INTERNAL_STATUS_DATA_REQUEST).

### -field RequestDataType

A [DEVICE_INTERNAL_STATUS_DATA_REQUEST_TYPE](ne-ntddstor-device_internal_status_data_request_type.md) enumeration that identifies the data type being requested.

### -field RequestDataSet

A [DEVICE_INTERNAL_STATUS_DATA_SET](ne-ntddstor-device_internal_status_data_set.md) enumeration that identifies the device status data set.

## -remarks

GET_DEVICE_INTERNAL_STATUS_DATA_REQUEST is the input buffer for [IOCTL_STORAGE_GET_DEVICE_INTERNAL_LOG](ni-ntddstor-ioctl_storage_get_device_internal_log.md).

## -see-also

[DEVICE_INTERNAL_STATUS_DATA](ns-ntddstor-device_internal_status_data.md)

[DEVICE_INTERNAL_STATUS_DATA_REQUEST_TYPE](ne-ntddstor-device_internal_status_data_request_type.md)

[DEVICE_INTERNAL_STATUS_DATA_SET](ne-ntddstor-device_internal_status_data_set.md)

[IOCTL_STORAGE_GET_DEVICE_INTERNAL_LOG](ni-ntddstor-ioctl_storage_get_device_internal_log.md)

