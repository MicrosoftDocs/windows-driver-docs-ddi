---
UID: NS:ntddstor._DEVICE_STORAGE_ADDRESS_RANGE
title: DEVICE_STORAGE_ADDRESS_RANGE
description: The DEVICE_STORAGE_ADDRESS_RANGE structure contains a physical address range.
tech.root: storage
ms.assetid: 99d86070-e24f-4e3f-8e62-be93fc9cfd21
ms.date: 08/23/2019
keywords: ["DEVICE_STORAGE_ADDRESS_RANGE structure"]
ms.keywords: DEVICE_STORAGE_ADDRESS_RANGE, DEVICE_STORAGE_ADDRESS_RANGE, *PDEVICE_STORAGE_ADDRESS_RANGE,
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
req.typenames: DEVICE_STORAGE_ADDRESS_RANGE, *PDEVICE_STORAGE_ADDRESS_RANGE
targetos: Windows
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - DEVICE_STORAGE_ADDRESS_RANGE
product:
 - Windows
f1_keywords:
 - _DEVICE_STORAGE_ADDRESS_RANGE
 - ntddstor/_DEVICE_STORAGE_ADDRESS_RANGE
 - PDEVICE_STORAGE_ADDRESS_RANGE
 - ntddstor/PDEVICE_STORAGE_ADDRESS_RANGE
 - DEVICE_STORAGE_ADDRESS_RANGE
 - ntddstor/DEVICE_STORAGE_ADDRESS_RANGE
---

# DEVICE_STORAGE_ADDRESS_RANGE structure


## -description

The DEVICE_STORAGE_ADDRESS_RANGE structure contains a physical address range.

## -struct-fields

### -field StartAddress

Starting address of the physical address range.

### -field LengthInBytes

Length of the physical address range, in bytes.

## -remarks

The output block in the payload of an [IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_manage_data_set_attributes) request is formatted as a [DEVICE_DSM_PHYSICAL_ADDRESSES_OUTPUT](ns-ntddstor-_device_dsm_physical_addresses_output.md) structure when the action is **DeviceDsmAction_GetPhysicalAddresses**. The driver returns the requested physical address ranges in an array of DEVICE_STORAGE_ADDRESS_RANGE structures. See [DEVICE_DSM_ACTION Descriptions](https://docs.microsoft.com/windows-hardware/drivers/storage/device-dsm-action-descriptions) for more details about this action.

## -see-also

[DEVICE_DSM_ACTION Descriptions](https://docs.microsoft.com/windows-hardware/drivers/storage/device-dsm-action-descriptions)

[DEVICE_DSM_PHYSICAL_ADDRESSES_OUTPUT](ns-ntddstor-_device_dsm_physical_addresses_output.md)

[IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_manage_data_set_attributes)

