---
UID: NS:ntddstor._STORAGE_DEVICE_POWER_CAP
title: STORAGE_DEVICE_POWER_CAP (ntddstor.h)
description: This structure is used as an input and output buffer for the IOCTL_STORAGE_DEVICE_POWER_CAP.
old-location: storage\storage_device_power_cap.htm
tech.root: storage
ms.date: 10/11/2022
keywords: ["STORAGE_DEVICE_POWER_CAP structure"]
ms.keywords: "*PSTORAGE_DEVICE_POWER_CAP, PSTORAGE_DEVICE_POWER_CAP, PSTORAGE_DEVICE_POWER_CAP structure pointer [Storage Devices], STORAGE_DEVICE_POWER_CAP, STORAGE_DEVICE_POWER_CAP structure [Storage Devices], _STORAGE_DEVICE_POWER_CAP, ntddstor/PSTORAGE_DEVICE_POWER_CAP, ntddstor/STORAGE_DEVICE_POWER_CAP, storage.storage_device_power_cap"
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: STORAGE_DEVICE_POWER_CAP, *PSTORAGE_DEVICE_POWER_CAP
f1_keywords:
 - _STORAGE_DEVICE_POWER_CAP
 - ntddstor/_STORAGE_DEVICE_POWER_CAP
 - PSTORAGE_DEVICE_POWER_CAP
 - ntddstor/PSTORAGE_DEVICE_POWER_CAP
 - STORAGE_DEVICE_POWER_CAP
 - ntddstor/STORAGE_DEVICE_POWER_CAP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _STORAGE_DEVICE_POWER_CAP
 - PSTORAGE_DEVICE_POWER_CAP
 - STORAGE_DEVICE_POWER_CAP
ms.custom: engagement-fy23 
---

# STORAGE_DEVICE_POWER_CAP structure

## -description

This structure is used as an input and output buffer for the [**IOCTL_STORAGE_DEVICE_POWER_CAP**](ni-ntddstor-ioctl_storage_device_power_cap.md).

## -struct-fields

### -field Version

The version of this structure. This should be set to **STORAGE_DEVICE_POWER_CAP_VERSION_V1**.

### -field Size

The size of this structure, in bytes.

### -field Units

The units of the **MaxPower** value. This value can be either a percentage (0-100%) or an absolute value in milliwatts. The output buffer's **Units** value will match the value from the input buffer.

### -field MaxPower

On input, **MaxPower** specifies the desired maximum power consumption value for the storage device. On output, **MaxPower** contains the value of the actual maximum power consuption level of the device. The output buffer value may be equal to, less than, or greater than the desired threshold, depending on what the device supports.

## -see-also

[**IOCTL_STORAGE_DEVICE_POWER_CAP**](ni-ntddstor-ioctl_storage_device_power_cap.md)
