---
UID: NI:ehstorbandmgmt.IOCTL_EHSTOR_BANDMGMT_ERASE_ALL_BANDS
tech.root: storage
title: IOCTL_EHSTOR_BANDMGMT_ERASE_ALL_BANDS
ms.date: 05/24/2022
targetos: Windows
description: Learn more about the IOCTL_EHSTOR_BANDMGMT_ERASE_ALL_BANDS IOCTL.
prerelease: false
req.construct-type: ioctl
req.ddi-compliance: 
req.dll: 
req.header: ehstorbandmgmt.h
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ehstorbandmgmt.h
api_name:
 - IOCTL_EHSTOR_BANDMGMT_ERASE_ALL_BANDS
f1_keywords:
 - IOCTL_EHSTOR_BANDMGMT_ERASE_ALL_BANDS
 - ehstorbandmgmt/IOCTL_EHSTOR_BANDMGMT_ERASE_ALL_BANDS
dev_langs:
 - c++
helpviewer_keywords:
 - IOCTL_EHSTOR_BANDMGMT_ERASE_ALL_BANDS
---

## -description

The **IOCTL_EHSTOR_BANDMGMT_ERASE_ALL_BANDS** request cryptographically erases and resets the authentication keys for all configured bands.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

None.

### -inout-buffer-length

None.

### -status-block

One of the following values can be returned in the **Status** field.

| Status Value | Description |
| ------------ | ----------- |
| STATUS_SUCCESS                | All bands were successfully erased. |
| STATUS_INVALID_DEVICE_REQUEST | The storage device does not support band management. |
| STATUS_IO_DEVICE_ERROR        | Communication failed. The storage device might be incompatible with security protocols. |

## -remarks

**IOCTL_EHSTOR_BANDMGMT_ERASE_ALL_BANDS** cryptographically erases and resets the authentication key for each configured band on the storage device, one band at a time. If all configured bands are successfully erased, the IOCTL will return a success status. If erase fails for one or more configured band, the IOCTL will return the failure status from the first configured band for which an error occurred. In this case, a client should fall back to calling [**IOCTL_EHSTOR_BANDMGMT_ERASE_BAND**](ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_erase_band.md) for each configured band.

There is no atomicity guarantee provided for erasure across multiple configured bands. Thus, if a system or power failure occurs while this IOCTL is being processed, some configured bands might have been successfully erased while others might not have.

## -see-also

[**IOCTL_EHSTOR_BANDMGMT_ERASE_BAND**](ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_erase_band.md)
