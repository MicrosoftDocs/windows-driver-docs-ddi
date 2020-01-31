---
UID: NE:ntddstor._DEVICE_INTERNAL_STATUS_DATA_SET
title: DEVICE_INTERNAL_STATUS_DATA_SET
author: windows-driver-content
description: DEVICE_INTERNAL_STATUS_DATA_SET identifies the device internal status data set to query.
tech.root: storage
ms.assetid: 1357eabc-2d9f-410a-b79c-775c7e0f5c19
ms.author: windowsdriverdev
ms.date: 11/30/2019
ms.topic: enum
f1_keywords:
 - "ntddstor/DEVICE_INTERNAL_STATUS_DATA_SET"
ms.keywords: DEVICE_INTERNAL_STATUS_DATA_SET, DEVICE_INTERNAL_STATUS_DATA_SET, *PDEVICE_INTERNAL_STATUS_DATA_SET, 
req.header: ntddstor.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: DEVICE_INTERNAL_STATUS_DATA_SET, *PDEVICE_INTERNAL_STATUS_DATA_SET
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - ntddstor.h
api_name: 
 - DEVICE_INTERNAL_STATUS_DATA_SET
product: 
 - Windows
targetos: Windows
---

# DEVICE_INTERNAL_STATUS_DATA_SET enumeration

## -description

DEVICE_INTERNAL_STATUS_DATA_SET identifies the device internal status data set to query.

## -enum-fields

### -field DeviceStatusDataSetUndefined

Reserved; do not use.

### -field DeviceStatusDataSet1

This field corresponds to data set 1.

### -field DeviceStatusDataSet2

This field corresponds to data set 2.

### -field DeviceStatusDataSet3

This field corresponds to data set 3.

### -field DeviceStatusDataSet4

This field corresponds to data set 4.

### -field DeviceStatusDataSetMax

Maximum data set number.

## -remarks

DEVICE_INTERNAL_STATUS_DATA_SET is a member of the [GET_DEVICE_INTERNAL_STATUS_DATA_REQUEST](ns-ntddstor-get_device_internal_status_data_request.md) structure, which contains all information about the internal status data being requested through [IOCTL_STORAGE_GET_DEVICE_INTERNAL_LOG](ni-ntddstor-ioctl_storage_get_device_internal_log.md).

The [DEVICE_INTERNAL_STATUS_DATA_REQUEST_TYPE ](ne-ntddstor-device_internal_status_data_set.md) enum identifies the data request type associated with the data set identified by this enum.

See the SCSI specification for details.

## -see-also

[DEVICE_INTERNAL_STATUS_DATA_REQUEST_TYPE ](ne-ntddstor-device_internal_status_data_set.md)

[GET_DEVICE_INTERNAL_STATUS_DATA_REQUEST](ns-ntddstor-get_device_internal_status_data_request.md)

[IOCTL_STORAGE_GET_DEVICE_INTERNAL_LOG](ni-ntddstor-ioctl_storage_get_device_internal_log.md)
