---
UID: NS:ntddstor._DEVICE_STORAGE_RANGE_ATTRIBUTES
title: DEVICE_STORAGE_RANGE_ATTRIBUTES
description: 
tech.root: storage
ms.date: 08/23/2019
keywords: ["DEVICE_STORAGE_RANGE_ATTRIBUTES structure"]
ms.keywords: DEVICE_STORAGE_RANGE_ATTRIBUTES, DEVICE_STORAGE_RANGE_ATTRIBUTES, *PDEVICE_STORAGE_RANGE_ATTRIBUTES,
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
req.typenames: DEVICE_STORAGE_RANGE_ATTRIBUTES, *PDEVICE_STORAGE_RANGE_ATTRIBUTES
targetos: Windows
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _DEVICE_STORAGE_RANGE_ATTRIBUTES
 - PDEVICE_STORAGE_RANGE_ATTRIBUTES
 - DEVICE_STORAGE_RANGE_ATTRIBUTES
product:
 - Windows
f1_keywords:
 - _DEVICE_STORAGE_RANGE_ATTRIBUTES
 - ntddstor/_DEVICE_STORAGE_RANGE_ATTRIBUTES
 - PDEVICE_STORAGE_RANGE_ATTRIBUTES
 - ntddstor/PDEVICE_STORAGE_RANGE_ATTRIBUTES
 - DEVICE_STORAGE_RANGE_ATTRIBUTES
 - ntddstor/DEVICE_STORAGE_RANGE_ATTRIBUTES
---

# DEVICE_STORAGE_RANGE_ATTRIBUTES structure


## -description

The DEVICE_STORAGE_RANGE_ATTRIBUTES structure contains the media error status for a logical block range.

## -struct-fields

### -field LengthInBytes

Length of the logical block range, in bytes, that the error status in *IsRangeBad* applies to.

### -field AllFlags

Do not use.

### -field IsRangeBad

Indicates whether the logical block range contains a media error. Set to 1 when the logical block range contains an error; otherwise, set to 0.

### -field Reserved

Reserved for future use; do not use.

## -remarks

The output block in the payload of an [IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](./ni-ntddstor-ioctl_storage_manage_data_set_attributes.md) request is formatted as a [DEVICE_DSM_RANGE_ERROR_OUTPUT](./ns-ntddstor-_device_dsm_range_error_info.md) structure when the action is **DeviceDsmAction_GetRangeErrorInfo**. The driver returns the error status for the logical block ranges in an array of DEVICE_STORAGE_RANGE_ATTRIBUTES structures. The array elements are sorted so that their order corresponds to the order of the input ranges.

See [DEVICE_DSM_ACTION Descriptions](/windows-hardware/drivers/storage/device-dsm-action-descriptions) for more details about this action.

## -see-also

[DEVICE_DSM_ACTION Descriptions](/windows-hardware/drivers/storage/device-dsm-action-descriptions)

[DEVICE_DSM_RANGE_ERROR_OUTPUT](./ns-ntddstor-_device_dsm_range_error_info.md)

[IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](./ni-ntddstor-ioctl_storage_manage_data_set_attributes.md)

