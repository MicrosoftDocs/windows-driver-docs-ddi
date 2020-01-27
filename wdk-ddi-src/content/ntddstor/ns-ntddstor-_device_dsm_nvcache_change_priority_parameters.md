---
UID: NS:ntddstor._DEVICE_DSM_NVCACHE_CHANGE_PRIORITY_PARAMETERS
title: DEVICE_DSM_NVCACHE_CHANGE_PRIORITY_PARAMETERS
author: windows-driver-content
description: The DEVICE_DSM_NVCACHE_CHANGE_PRIORITY_PARAMETERS structure contains caching priority information to apply to a range of logical blocks.
tech.root: storage
f1_keywords:
 - "ntddstor/DEVICE_DSM_NVACHE_CHANGE_PRIORITY_PARAMETERS"
ms.assetid: 97a840df-0648-416e-a4b3-e3e4e57018ab
ms.author: windowsdriverdev
ms.date: 08/23/2019
ms.keywords: DEVICE_DSM_NVCACHE_CHANGE_PRIORITY_PARAMETERS, DEVICE_DSM_NVCACHE_CHANGE_PRIORITY_PARAMETERS, *PDEVICE_DSM_NVCACHE_CHANGE_PRIORITY_PARAMETERS, 
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
req.typenames: DEVICE_DSM_NVCACHE_CHANGE_PRIORITY_PARAMETERS, *PDEVICE_DSM_NVCACHE_CHANGE_PRIORITY_PARAMETERS
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - ntddstor.h
api_name: 
 - DEVICE_DSM_NVCACHE_CHANGE_PRIORITY_PARAMETERS
product: 
 - Windows
targetos: Windows
---

# DEVICE_DSM_NVCACHE_CHANGE_PRIORITY_PARAMETERS structure

## -description

The DEVICE_DSM_NVCACHE_CHANGE_PRIORITY_PARAMETERS structure contains caching priority information to apply to a range of logical blocks.

## -struct-fields

### -field Size

Size of this structure. Set to **sizeof**(DEVICE_DSM_NVCACHE_CHANGE_PRIORITY_PARAMETERS).

### -field TargetPriority

The target caching priority to apply to a range of logical blocks.

### -field Reserved

Reserved for future use; do not use.

## -remarks

The output block in the payload of an [IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_manage_data_set_attributes) request is formatted as a DEVICE_DSM_NVCACHE_CHANGE_PRIORITY_PARAMETERS structure when the action is **DeviceDsmAction_NvCache_Change_Priority**. See [DEVICE_DSM_ACTION Descriptions](https://docs.microsoft.com/windows-hardware/drivers/storage/device-dsm-action-descriptions) for more details about this action.

## -see-also

[DEVICE_DSM_ACTION Descriptions](https://docs.microsoft.com/windows-hardware/drivers/storage/device-dsm-action-descriptions)

[IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_manage_data_set_attributes)
