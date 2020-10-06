---
UID: NS:ntddstor._DEVICE_DSM_PHYSICAL_ADDRESSES_OUTPUT
title: DEVICE_DSM_PHYSICAL_ADDRESSES_OUTPUT
description: The DEVICE_DSM_PHYSICAL_ADDRESSES_OUTPUT structure stores physical address ranges that correspond with one or more logical block ranges.
tech.root: storage
ms.assetid: 0eb514dd-588f-41ee-bd30-5dad00c19141
ms.date: 08/23/2019
keywords: ["DEVICE_DSM_PHYSICAL_ADDRESSES_OUTPUT structure"]
ms.keywords: DEVICE_DSM_PHYSICAL_ADDRESSES_OUTPUT, DEVICE_DSM_PHYSICAL_ADDRESSES_OUTPUT, *PDEVICE_DSM_PHYSICAL_ADDRESSES_OUTPUT,
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
req.typenames: DEVICE_DSM_PHYSICAL_ADDRESSES_OUTPUT, *PDEVICE_DSM_PHYSICAL_ADDRESSES_OUTPUT
targetos: Windows
f1_keywords:
 - _DEVICE_DSM_PHYSICAL_ADDRESSES_OUTPUT
 - ntddstor/_DEVICE_DSM_PHYSICAL_ADDRESSES_OUTPUT
 - PDEVICE_DSM_PHYSICAL_ADDRESSES_OUTPUT
 - ntddstor/PDEVICE_DSM_PHYSICAL_ADDRESSES_OUTPUT
 - DEVICE_DSM_PHYSICAL_ADDRESSES_OUTPUT
 - ntddstor/DEVICE_DSM_PHYSICAL_ADDRESSES_OUTPUT
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - DEVICE_DSM_PHYSICAL_ADDRESSES_OUTPUT
product:
 - Windows
---

# DEVICE_DSM_PHYSICAL_ADDRESSES_OUTPUT structure


## -description

The DEVICE_DSM_PHYSICAL_ADDRESSES_OUTPUT structure stores physical address ranges that correspond with one or more logical block ranges.

## -struct-fields

### -field Version

Version of this structure. Set to **sizeof**(DEVICE_DSM_PHYSICAL_ADDRESSES_OUTPUT).

### -field Flags

Reserved for future use; do not use.

### -field TotalNumberOfRanges

Number of [DEVICE_STORAGE_ADDRESS_RANGE](ns-ntddstor_device_storage_address_range.md) structure(s) needed to satisfy a **DeviceDsmAction_GetPhysicalAddresses** request.

### -field NumberOfRangesReturned

Number of physical address ranges returned in *Ranges*.

### -field Ranges

Array of DEVICE_STORAGE_ADDRESS_RANGE structure(s) in which to return physical address ranges.

## -remarks

The output block in the payload of an [IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](./ni-ntddstor-ioctl_storage_manage_data_set_attributes.md) request is formatted as a DEVICE_DSM_PHYSICAL_ADDRESSES_OUTPUT structure when the action is **DeviceDsmAction_GetPhysicalAddresses**. See [DEVICE_DSM_ACTION Descriptions](/windows-hardware/drivers/storage/device-dsm-action-descriptions) for more details about this action.

## -see-also

[DEVICE_DSM_ACTION Descriptions](/windows-hardware/drivers/storage/device-dsm-action-descriptions)

[DEVICE_STORAGE_ADDRESS_RANGE](ns-ntddstor_device_storage_address_range.md)

[IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](./ni-ntddstor-ioctl_storage_manage_data_set_attributes.md)