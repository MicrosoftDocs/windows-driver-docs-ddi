---
UID: NF:ntddstor.DeviceDsmAddDataSetRange
title: DeviceDsmAddDataSetRange function (ntddstor.h)
description: The DeviceDsmAddDataSetRange function adds a data set range to a DEVICE_DSM_INPUT structure.
tech.root: storage
ms.date: 08/23/2019
keywords: ["DeviceDsmAddDataSetRange function"]
ms.keywords: DeviceDsmAddDataSetRange
req.header: ntddstor.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - DeviceDsmAddDataSetRange
 - ntddstor/DeviceDsmAddDataSetRange
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - DeviceDsmAddDataSetRange
---

# DeviceDsmAddDataSetRange function


## -description

The **DeviceDsmAddDataSetRange** function adds a data set range to the system buffer for an [IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](./ni-ntddstor-ioctl_storage_manage_data_set_attributes.md) request.

## -parameters

### -param Input

Pointer to the [DEVICE_DSM_INPUT](ns-ntddstor-_device_manage_data_set_attributes.md) structure to which to add the data set range.

### -param InputLength

The length, in bytes, of the entire payload of the IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES request.

### -param Offset

The offset from the start of the DEVICE_DSM_INPUT structure at which the data set range starts, in bytes.

### -param Length

The length, in bytes, of the data set range.

## -returns

Returns TRUE if the data set range was successfully added, or FALSE otherwise.

## -remarks

If the DSM has range data, call **DeviceDsmAddDataSetRange** for each range to add it to the system buffer. See [Data Set Management Overview](/windows-hardware/drivers/storage/data-set-management-overview) for the layout of the system buffer for an [IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](./ni-ntddstor-ioctl_storage_manage_data_set_attributes.md) request.

## -see-also

[Data Set Management Overview](/windows-hardware/drivers/storage/data-set-management-overview)

[DEVICE_DSM_INPUT](ns-ntddstor-_device_manage_data_set_attributes.md)

[DEVICE_DSM_RANGE](ns-ntddstor-_device_data_set_range.md)

[IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](./ni-ntddstor-ioctl_storage_manage_data_set_attributes.md)
