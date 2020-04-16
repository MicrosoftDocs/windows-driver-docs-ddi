---
UID: NS:ntddstor._DEVICE_DSM_RANGE_ERROR_INFO
title: DEVICE_DSM_RANGE_ERROR_INFO
author: windows-driver-content
description: The DEVICE_DSM_RANGE_ERROR_OUTPUT (or DEVICE_DSM_RANGE_ERROR_INFO) structure stores information about whether one or more logical block ranges contain any media errors.
tech.root: storage
ms.assetid: 23b635e6-0e49-4207-a46f-5b632de643bf
ms.author: windowsdriverdev
ms.date: 08/23/2019
keywords: ["DEVICE_DSM_RANGE_ERROR_INFO structure"]
ms.keywords: DEVICE_DSM_RANGE_ERROR_INFO, DEVICE_DSM_RANGE_ERROR_INFO, *PDEVICE_DSM_RANGE_ERROR_INFO, DEVICE_DSM_RANGE_ERROR_OUTPUT, *PDEVICE_DSM_RANGE_ERROR_OUTPUT, 
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
req.typenames: DEVICE_DSM_RANGE_ERROR_INFO, *PDEVICE_DSM_RANGE_ERROR_INFO, DEVICE_DSM_RANGE_ERROR_OUTPUT, *PDEVICE_DSM_RANGE_ERROR_OUTPUT
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - ntddstor.h
api_name: 
 - DEVICE_DSM_RANGE_ERROR_INFO
product: 
 - Windows
targetos: Windows
---

# DEVICE_DSM_RANGE_ERROR_INFO structure

## -description

The **DEVICE_DSM_RANGE_ERROR_OUTPUT** (or DEVICE_DSM_RANGE_ERROR_INFO) structure stores information about whether one or more logical block ranges contain any media errors.

## -struct-fields

### -field Version

Version of this structure. Set to **sizeof**(DEVICE_DSM_RANGE_ERROR_OUTPUT).

### -field Flags

Flags associated with the range error information. Possible values are:

| Value | Meaning |
| ----- | ------- |
| DEVICE_STORAGE_NO_ERRORS | There are no media errors in any of the requested ranges. |

### -field TotalNumberOfRanges

Number of [DEVICE_STORAGE_RANGE_ATTRIBUTES](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor_device_storage_range_attributes) structure(s) needed to satisfy a **DeviceDsmAction_GetRangeErrorInfo** request.

### -field NumberOfRangesReturned

Number of DEVICE_STORAGE_RANGE_ATTRIBUTES structures returned in *Ranges*.

### -field Ranges

Array of DEVICE_STORAGE_RANGE_ATTRIBUTES structure(s) in which to return media error information.

## -remarks

The output block in the payload of an [IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_manage_data_set_attributes) request is formatted as a DEVICE_DSM_RANGE_ERROR_OUTPUT structure when the action is **DeviceDsmAction_GetRangeErrorInfo**. See [DEVICE_DSM_ACTION Descriptions](https://docs.microsoft.com/windows-hardware/drivers/storage/device-dsm-action-descriptions) for more details about this action.

## -see-also

[DEVICE_DSM_ACTION Descriptions](https://docs.microsoft.com/windows-hardware/drivers/storage/device-dsm-action-descriptions)

[DEVICE_STORAGE_RANGE_ATTRIBUTES](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor_device_storage_range_attributes)

[IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_manage_data_set_attributes)
