---
UID: NE:ntddstor._DEVICE_INTERNAL_STATUS_DATA_REQUEST_TYPE
title: DEVICE_INTERNAL_STATUS_DATA_REQUEST_TYPE
description: DEVICE_INTERNAL_STATUS_DATA_REQUEST_TYPE identifies the data type to be queried.
tech.root: storage
ms.date: 11/30/2019
ms.topic: enum
ms.keywords: DEVICE_INTERNAL_STATUS_DATA_REQUEST_TYPE, DEVICE_INTERNAL_STATUS_DATA_REQUEST_TYPE, *PDEVICE_INTERNAL_STATUS_DATA_REQUEST_TYPE,
req.header: ntddstor.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: DEVICE_INTERNAL_STATUS_DATA_REQUEST_TYPE, *PDEVICE_INTERNAL_STATUS_DATA_REQUEST_TYPE
targetos: Windows
f1_keywords:
 - _DEVICE_INTERNAL_STATUS_DATA_REQUEST_TYPE
 - ntddstor/_DEVICE_INTERNAL_STATUS_DATA_REQUEST_TYPE
 - PDEVICE_INTERNAL_STATUS_DATA_REQUEST_TYPE
 - ntddstor/PDEVICE_INTERNAL_STATUS_DATA_REQUEST_TYPE
 - DEVICE_INTERNAL_STATUS_DATA_REQUEST_TYPE
 - ntddstor/DEVICE_INTERNAL_STATUS_DATA_REQUEST_TYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _DEVICE_INTERNAL_STATUS_DATA_REQUEST_TYPE
 - PDEVICE_INTERNAL_STATUS_DATA_REQUEST_TYPE
 - DEVICE_INTERNAL_STATUS_DATA_REQUEST_TYPE
product:
 - Windows
---

# DEVICE_INTERNAL_STATUS_DATA_REQUEST_TYPE enumeration


## -description

The DEVICE_INTERNAL_STATUS_DATA_REQUEST_TYPE enum identifies the internal status data type being queried.

## -enum-fields

### -field DeviceInternalStatusDataRequestTypeUndefined

Reserved; do not use.

### -field DeviceCurrentInternalStatusDataHeader

Query the device's internal status data header. The data header size is always 512 bytes. Refer to the SCSI specification for more details about the header format.

### -field DeviceCurrentInternalStatusData

Query the device's internal status data. The data block size is always a multiple of 512 bytes.

## -remarks

DEVICE_INTERNAL_STATUS_DATA_REQUEST_TYPE is a member of the [GET_DEVICE_INTERNAL_STATUS_DATA_REQUEST](ns-ntddstor-get_device_internal_status_data_request.md) structure, which contains all information about the internal status data being requested through [IOCTL_STORAGE_GET_DEVICE_INTERNAL_LOG](ni-ntddstor-ioctl_storage_get_device_internal_log.md).

The [DEVICE_INTERNAL_STATUS_DATA_SET](ne-ntddstor-device_internal_status_data_set.md) enum identifies the data set associated with the data request type.

## -see-also

[DEVICE_INTERNAL_STATUS_DATA_SET](ne-ntddstor-device_internal_status_data_set.md)

[GET_DEVICE_INTERNAL_STATUS_DATA_REQUEST](ns-ntddstor-get_device_internal_status_data_request.md)

[IOCTL_STORAGE_GET_DEVICE_INTERNAL_LOG](ni-ntddstor-ioctl_storage_get_device_internal_log.md)

